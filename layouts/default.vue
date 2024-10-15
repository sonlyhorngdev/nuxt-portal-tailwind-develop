<template>
  <div class="flex min-h-screen">
    <!-- Sidebar on the left -->
    <Sidebar :isOpen="sidebarOpen" class="w-64 z-0" />

    <div class="flex flex-col w-full">
      <!-- Header at the top -->
      <Header @toggle-sidebar="sidebarOpen = !sidebarOpen" class="h-16 z-10 relative" />

      <!-- Main content area -->
      <main class="flex-1 p-4 bg-gray-100">
        <NuxtPage />
      </main>

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
/* .sidebar {
        position: relative; 
        z-index: 1; 
      } */

/* Header Styles */
/* .header {
        position: relative; 
        z-index: 10;
      } */

/* Main Area */
/* main {
        position: relative;
        z-index: 0; 
      } */
/*       
      .min-h-screen {
        background-color: white;
      } */
</style>
