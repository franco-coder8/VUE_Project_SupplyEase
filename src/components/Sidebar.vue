<template>
    <div :class="['fixed top-0 left-0 h-full bg-gray-800 text-white w-64 transition-transform duration-300 md:translate-x-0', { 'translate-x-0': showSidebar, '-translate-x-full': !showSidebar }]">
      <div class="p-4 h-full flex flex-col">
        <div class="flex items-center justify-between mb-4">
          <h2 class="text-lg font-semibold text-white">Menu</h2>
          <button @click="toggleSidebar" class="text-white md:hidden">
            <svg class="w-6 h-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
        </div>
        <div class="flex-1 scrollbar-hidden">
          <ul>
            <li><a href="#" class="block px-4 py-2 hover:bg-gray-700">Dashboard</a></li>
            <li><router-link to="/procurement-management" class="block px-4 py-2 hover:bg-gray-700">Procurement Management</router-link></li>
            <li><a href="#" class="block px-4 py-2 hover:bg-gray-700">Order Management</a></li>
            <li><a href="#" class="block px-4 py-2 hover:bg-gray-700">Inventory Management</a></li>
            <li><a href="#" class="block px-4 py-2 hover:bg-gray-700">Supplier Management</a></li>
            <li><a href="#" class="block px-4 py-2 hover:bg-gray-700">Customer Management</a></li>
            <li><a href="#" class="block px-4 py-2 hover:bg-gray-700">Reports & Analytics</a></li>
            <li><a href="#" class="block px-4 py-2 hover:bg-gray-700">Settings and Configuration</a></li>
            <li><a href="#" class="block px-4 py-2 hover:bg-gray-700">Help & Support</a></li>
          </ul>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      showSidebar: Boolean
    },
    methods: {
      toggleSidebar() {
        this.$emit('toggle-sidebar');
      }
    }
  }
  </script>
  
  <style scoped>
  /* Ensure proper transition effect for sidebar */
  .transition-transform {
    transition: transform 0.3s ease-in-out;
  }
  
  /* Hide scrollbar but allow scrolling */
  .scrollbar-hidden {
    overflow: hidden; /* Hide scrollbars */
  }
  
  .scrollbar-hidden::-webkit-scrollbar {
    display: none; /* For Chrome, Safari, and Opera */
  }
  
  /* Flex layout for ensuring full height and scrolling */
  .flex-1 {
    flex: 1;
    overflow-y: auto; /* Ensure the content can scroll vertically */
  }
  
  /* Ensure sidebar appears above other elements */
  .fixed {
    z-index: 50; /* Adjust z-index as needed to ensure it is above the navbar */
  }
  </style>
  