<template>
    <div :class="{ 'bg-gray-200 text-gray-800': !isDarkMode, 'bg-gray-800 text-gray-100': isDarkMode }">
      <!-- Your Dashboard content goes here -->
      <!-- Add more content and components as needed -->
    </div>
  </template>
  
  <script>
  export default {
    props: {
      isDarkMode: Boolean
    }
  }
  </script>
  
  <style scoped>
  /* Dark mode styles for Dashboard */
  .bg-gray-200 {
    background-color: #edf2f7;
  }
  
  .bg-gray-800 {
    background-color: #2d3748;
  }
  
  .text-gray-800 {
    color: #2d3748;
  }
  
  .text-gray-100 {
    color: #edf2f7;
  }
  </style>
  