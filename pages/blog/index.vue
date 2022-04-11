<template>
  <div>
    <AppHeader />
    <GreyBox />
    <h1>blog</h1>
    <ul>
      <li v-for="article of articles" :key="article.slug">
        <NuxtLink class="article-style" :to="{ name: 'blog-slug', params: { slug: article.slug } }">
          <div>
            <h2>{{ article.title }}</h2>
            <p>{{ article.description }}</p>
          </div>
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script>
import AppHeader from "../../components/AppHeader.vue"
import GreyBox from "../../components/GreyBox.vue"
  export default {
    async asyncData({ $content, params }) {
        const articles = await $content("articles")
            .only(["title", "description", "slug"])
            .sortBy("createdAt", "asc")
            .fetch();
        return {
            articles
        };
    },
    components: { AppHeader, GreyBox }
}
</script>

<style>

</style>