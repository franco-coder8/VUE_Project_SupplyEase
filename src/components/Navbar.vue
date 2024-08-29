<template>
  <div :class="['fixed top-0 left-0 w-full p-4 transition-all duration-300', { 'bg-gray-800 text-white': !isDarkMode, 'bg-gray-900 text-gray-100': isDarkMode }]" >
    <div class="flex justify-between items-center">
      <!-- Burger Button for Sidebar -->
      <button @click="$emit('toggle-sidebar')" class="mr-4 md:hidden">
        <svg class="w-6 h-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7" />
        </svg>
      </button>

      <!-- Navbar Brand/Logo (Removed Dashboard) -->
      <div class="text-lg font-semibold"></div>

      <!-- Navbar Right Side -->
      <div class="flex items-center space-x-4">
        <!-- Dark Mode Toggle -->
        <button @click="$emit('toggle-dark-mode')" class="p-2 rounded">
          <svg :class="{'text-white': !isDarkMode, 'text-gray-100': isDarkMode}" class="w-6 h-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 3v9m0 0l-3-3m3 3l3-3" />
          </svg>
        </button>

        <!-- Profile Dropdown -->
        <div class="relative">
          <button @click="toggleDropdown" class="flex items-center justify-center w-10 h-10 rounded-full bg-gray-600 hover:bg-gray-700">
            <span class="text-xl text-gray-100">P</span> <!-- Placeholder for profile icon -->
          </button>
          <!-- Dropdown Menu -->
          <div v-if="showDropdown" class="absolute right-0 mt-2 w-48 rounded-md shadow-lg" :class="{ 'bg-white text-gray-800': !isDarkMode, 'bg-gray-800 text-gray-100': isDarkMode }">
            <a href="#" class="block px-4 py-2 hover:bg-gray-200 dark:hover:bg-gray-700">Edit Profile</a>
            <a href="#" class="block px-4 py-2 hover:bg-gray-200 dark:hover:bg-gray-700">Settings</a>
            <a href="#" class="block px-4 py-2 hover:bg-gray-200 dark:hover:bg-gray-700">Sign Out</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    isDarkMode: Boolean
  },
  data() {
    return {
      showDropdown: false
    };
  },
  methods: {
    toggleDropdown() {
      this.showDropdown = !this.showDropdown;
    }
  }
}
</script>

<style scoped>
/* Ensure the navbar spans the full width of the page */
.w-full {
  width: 100%;
}
</style>
