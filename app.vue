<template>
  <div class="flex min-h-screen">
    <!-- Sidebar on the left -->
    <Sidebar :isOpen="sidebarOpen" class="w-64 z-0 sidebar-left" />

    <!-- Main content area -->
    <div class="flex flex-col w-full">
      <!-- Header at the top -->
      <Header @toggle-sidebar="sidebarOpen = !sidebarOpen" class="header h-16 z-10" />

      <!-- Main content and right sidebar container -->
      <div class="flex flex-1 overflow-hidden">
        <!-- Main content (Scrollable) -->
        <main class="flex-1 p-4 overflow-y-auto">
          <NuxtPage />
        </main>

        <!-- Sidebar on the right -->
        <Sidebar :isOpen="sidebarOpen" class="w-64 z-0 sidebar-right" />
      </div>

      <!-- Footer at the bottom -->
      <Footer class="h-16" />
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import Header from '~/components/Header.vue';
import Sidebar from '~/components/Sidebar.vue';
import Footer from '~/components/Footer.vue';

const sidebarOpen = ref(false);
</script>

<style scoped>
/* Sidebar Styles */
.sidebar-left {
  background-color: rgb(0, 204, 240);
}

.sidebar-right {
  background-color: rgb(240, 204, 0); /* Different color for the right sidebar */
}

/* Header Styles */
.header {
  position: sticky;
  top: 0;
  z-index: 50;
  background-color: white;
}

/* Main Area (Scrollable) */
main {
  position: relative;
  z-index: 0;
  background-color: rgb(19, 172, 214);
  overflow-y: auto; /* Enables scrolling within the main content */
}

/* Footer Styles */
footer {
  background-color: #333;
  color: white;
  text-align: center;
  line-height: 16px;
}

/* Fixes the content container so it doesn't scroll with the header */
.flex-1 {
  overflow-y: auto;
  height: calc(100vh - 4rem); /* Adjust based on header and footer heights */
}
</style>
