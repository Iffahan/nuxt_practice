<template>
    <div class="flex flex-col items-center justify-center min-h-screen bg-gray-100">
        <h1 class="text-4xl font-bold mb-8">Todo List</h1>
        <div v-if="loading" class="text-2xl">Loading...</div>
        <div v-else class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
            <div v-for="todo in todos" :key="todo.id" class="bg-white p-6 rounded-lg shadow-md">
                <h2 class="text-xl font-semibold mb-2">{{ todo.title }}</h2>
                <p :class="{ 'text-green-600': todo.completed, 'text-red-600': !todo.completed }">
                    {{ todo.completed ? 'Completed' : 'Not Completed' }}
                </p>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'

interface Todo {
    userId: number;
    id: number;
    title: string;
    completed: boolean;
}

export default Vue.extend({
    data() {
        return {
            todos: [] as Todo[],
            loading: true,
        }
    },
    async mounted() {
        try {
            const response = await this.$axios.$get<Todo[]>('https://jsonplaceholder.typicode.com/todos')
            this.todos = response.slice(0, 12)
        } catch (error) {
            console.error('Error fetching todos:', error)
        } finally {
            this.loading = false
        }
    },
})
</script>
