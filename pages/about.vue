<template>
    <div class="flex flex-col items-center justify-center min-h-screen bg-gradient-to-r from-green-500 to-blue-500">
        <h1 class="text-3xl font-bold text-white">About Page</h1>
        <p class="mt-4 text-xl text-white">Welcome to the About Page!</p>
        <nuxt-link to="/" class="mt-4 text-white underline">
            Go to Index Page
        </nuxt-link>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
    name: 'AboutPage',
})
</script>
