<template>
  <div
    class="flex flex-col items-center justify-center min-h-screen bg-gradient-to-r from-blue-500 to-purple-500 space-y-8">
    <h1 class="text-2xl font-bold text-white">{{ message }}</h1>

    <!-- Counter 1: Using Local State -->

    <div class="bg-white p-8 rounded-lg shadow-lg flex items-center justify-between w-64 h-24">
      <h1>Local State</h1>
      <button @click="decrementCount"
        class="px-4 py-2 bg-red-500 text-white font-bold rounded-md hover:bg-red-600 transition-colors duration-200">
        -
      </button>
      <p class="text-3xl font-semibold text-gray-800 w-16 text-center">
        {{ count }}
      </p>
      <button @click="incrementCount"
        class="px-4 py-2 bg-green-500 text-white font-bold rounded-md hover:bg-green-600 transition-colors duration-200">
        +
      </button>
    </div>

    <!-- Counter 2: Using Vuex Store -->
    <div class="bg-white p-8 rounded-lg shadow-lg flex items-center justify-between w-64 h-24">
      <h1>Vuex Store</h1>
      <button @click="decrementStoreCount"
        class="px-4 py-2 bg-red-500 text-white font-bold rounded-md hover:bg-red-600 transition-colors duration-200">
        -
      </button>
      <p class="text-3xl font-semibold text-gray-800 w-16 text-center">
        {{ storeCount }}
      </p>
      <button @click="incrementStoreCount"
        class="px-4 py-2 bg-green-500 text-white font-bold rounded-md hover:bg-green-600 transition-colors duration-200">
        +
      </button>
    </div>

    <nuxt-link to="/about" class="mt-4 text-white underline">
      Go to About Page
    </nuxt-link>
    <nuxt-link to="/todos" class="mt-4 text-white underline">
      Go to Todos Page
    </nuxt-link>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { mapState, mapMutations } from 'vuex'

export default Vue.extend({
  name: 'IndexPage',
  data() {
    return {
      count: 0, // Local state for first counter
      message: 'Hello from TypeScript!',
    }
  },
  computed: {
    ...mapState({
      storeCount: (state: any) => state.counter // Vuex state for second counter
    })
  },
  methods: {
    incrementCount() {
      this.count++
    },
    decrementCount() {
      this.count--
    },
    ...mapMutations({
      incrementStoreCount: 'increment',
      decrementStoreCount: 'decrement'
    })
  },
})
</script>
