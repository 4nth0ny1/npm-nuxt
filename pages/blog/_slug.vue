<template>
    <article>
    <AppHeader />
    <!-- <nav>
        <ul>
            <li v-for="link of article.toc" :key="link.id">
            <NuxtLink :to="`#${link.id}`">{{ link.text }}</NuxtLink>
            </li>
        </ul>
    </nav> -->
    <h1>{{ article.title }}</h1>
    <p>{{ article.description }}</p>
    <p>{{ article.cool }}</p>

    <nuxt-content :document="article" />

    <prev-next :prev="prev" :next="next" />
  </article>
</template>

<script>
import AppHeader from "../../components/AppHeader.vue"
export default {
    async asyncData({ $content, params }) {
        const article = await $content("articles", params.slug).fetch();
        return { article };
    },
    components: { AppHeader }
}
</script>

<style>

</style>