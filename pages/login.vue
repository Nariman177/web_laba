<template>
  <div class="flex items-center justify-center min-h-screen bg-gradient-to-br from-indigo-100 to-white">
    <div class="bg-white shadow-2xl rounded-2xl p-10 w-96 text-center">
      <h1 class="text-3xl font-semibold mb-6 text-indigo-600">Welcome Back 🌿</h1>
      <form @submit.prevent="login">
        <input
          v-model="email"
          type="email"
          placeholder="Email"
          required
          class="w-full mb-4 px-4 py-2 border border-gray-300 rounded-xl focus:outline-none focus:ring-2 focus:ring-indigo-300"
        />
        <input
          v-model="password"
          type="password"
          placeholder="Password"
          required
          class="w-full mb-6 px-4 py-2 border border-gray-300 rounded-xl focus:outline-none focus:ring-2 focus:ring-indigo-300"
        />
        <button
          type="submit"
          class="w-full bg-indigo-500 hover:bg-indigo-600 text-white py-2 rounded-xl transition duration-300"
        >
          Log In
        </button>
      </form>
      <p class="mt-4 text-gray-500 text-sm">
        Don’t have an account?
        <a href="/register" class="text-indigo-600 hover:underline">Sign up</a>
      </p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const email = ref('')
const password = ref('')

function login() {
  console.log('Logged in as:', email.value)
}
</script>
