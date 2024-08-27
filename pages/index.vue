<template>
  <div class="flex flex-col items-center justify-center min-h-screen bg-gradient-to-r from-blue-500 to-purple-500">
    <div class="bg-white p-8 rounded-lg shadow-lg flex items-center justify-between w-64 h-24">
      <button
        @click="decrementCount"
        class="px-4 py-2 bg-red-500 text-white font-bold rounded-md hover:bg-red-600 transition-colors duration-200"
      >
        -
      </button>
      <p class="text-3xl font-semibold text-gray-800 w-16 text-center">
        {{ count }}
      </p>
      <button
        @click="incrementCount"
        class="px-4 py-2 bg-green-500 text-white font-bold rounded-md hover:bg-green-600 transition-colors duration-200"
      >
        +
      </button>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'CounterPage',
  data() {
    return {
      count: 0,
    }
  },
  methods: {
    incrementCount() {
      this.count++
    },
    decrementCount() {
      this.count--
    },
  },
})
</script>
