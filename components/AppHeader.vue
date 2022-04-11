<template>
    <div class="navbar">
        <ul>
            <NuxtLink class="nuxt-link" to="/">home</NuxtLink>
            <NuxtLink class="nuxt-link" to="/about">about</NuxtLink>
            <NuxtLink class="nuxt-link" to="/blog">blog</NuxtLink>
            <NuxtLink class="nuxt-link" to="/contact">contact</NuxtLink>
        </ul>
    </div>
</template>

<script>
export default {

}
</script>

<style>
.navbar {
    background: black;
    /* border-bottom: 1px solid gray; */
    box-shadow: 1px 1px 1px 1px gray;
}

ul {
    display: flex;
    flex-direction: row;
    justify-content: end;
}

.nuxt-link {
    padding: 10px;
    text-decoration: none;
    color: white;
}

</style>