<template>
    <div
        class="flex flex-col items-center justify-center min-h-screen bg-gradient-to-r from-green-500 to-blue-500 space-y-4">
        <h1 class="text-3xl font-bold text-white">About Page</h1>
        <p class="mt-4 text-xl text-white">Welcome to the About Page!</p>
        <p class="mt-4 text-xl text-white">Current Count: {{ storeCount }}</p> <!-- Display storeCount -->

        <nuxt-link to="/" class="mt-4 text-white underline">
            Go to Index Page
        </nuxt-link>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { mapState } from 'vuex'

export default Vue.extend({
    name: 'AboutPage',
    computed: {
        ...mapState({
            storeCount: (state: any) => state.counter // Access Vuex state
        })
    }
})
</script>
