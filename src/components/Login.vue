<template>
    <div class="flex justify-center items-center min-h-screen bg-gray-100 dark:bg-gray-900">
      <div class="w-full max-w-md p-8 bg-white dark:bg-gray-800 shadow-md rounded-lg">
        <h2 class="text-2xl font-bold mb-4 text-gray-900 dark:text-gray-100">Sign In</h2>
        <form @submit.prevent="handleSubmit">
          <div class="mb-4">
            <label for="email" class="block text-gray-700 dark:text-gray-300">Email</label>
            <input type="email" id="email" v-model="email" class="w-full p-2 border rounded" required />
          </div>
          <div class="mb-4">
            <label for="password" class="block text-gray-700 dark:text-gray-300">Password</label>
            <input type="password" id="password" v-model="password" class="w-full p-2 border rounded" required />
          </div>
          <button type="submit" class="w-full bg-blue-500 text-white p-2 rounded">Sign In</button>
        </form>
        <p class="mt-4 text-gray-700 dark:text-gray-300">
          Don't have an account? <router-link to="/register" class="text-blue-500">Register</router-link>
        </p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        email: '',
        password: ''
      };
    },
    methods: {
      handleSubmit() {
        // Handle login logic here
        console.log('Logged in with', this.email, this.password);
      }
    }
  }
  </script>
  
  <style scoped>
  /* Add any additional styling if needed */
  </style>
  