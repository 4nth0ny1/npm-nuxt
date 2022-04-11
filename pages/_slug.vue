<template>
    <div>
        <AppHeader />
        <GreyBox />
        <nuxt-content :document="doc" />
    </div>
</template>

<script>
import GreyBox from "../components/GreyBox.vue"
export default {
    async asyncData({ $content, params }) {
        const doc = await $content(params.slug || "index").fetch();
        return { doc };
    },
    components: { GreyBox }
}
</script>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
</style>