<template>
  <div :class="{ 'dark-mode': isDarkMode }">
    <Navbar @toggle-dark-mode="toggleDarkMode" @toggle-sidebar="toggleSidebar" />
    <Sidebar :showSidebar="showSidebar" @toggle-sidebar="toggleSidebar" />
    <div class="pt-16"> <!-- Padding to account for fixed navbar -->
      <div class="dashboard-content p-4">
        <router-view /> <!-- This will dynamically load the selected view -->
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import Sidebar from './components/Sidebar.vue';

export default {
  components: {
    Navbar,
    Sidebar
  },
  data() {
    return {
      showSidebar: false,
      isDarkMode: false // Default to light mode
    };
  },
  methods: {
    toggleSidebar() {
      this.showSidebar = !this.showSidebar;
    },
    toggleDarkMode() {
      this.isDarkMode = !this.isDarkMode;
      document.body.classList.toggle('dark-mode', this.isDarkMode);
    }
  }
}
</script>

<style>
body.dark-mode {
  background-color: #1a202c;
  color: #e2e8f0;
}

.dark-mode .navbar {
  background-color: #2d3748;
}

.dark-mode .sidebar {
  background-color: #1a202b;
}

.dashboard-content {
  transition: background-color 0.3s, color 0.3s;
}
</style>
