<template>
    <main class="p-4 md:ml-64 h-auto pt-20">
        <div class="border-2 border-dashed rounded-lg border-gray-300 dark:border-gray-600 h-96 mb-4 w-full py-32"></div>
        <div class="border-2 border-dashed rounded-lg border-gray-300 dark:border-gray-600 h-96 mb-4 w-full py-32"></div>
        <div class="border-2 border-dashed rounded-lg border-gray-300 dark:border-gray-600 h-96 mb-4 w-full py-32"></div>
        <div class="border-2 border-dashed rounded-lg border-gray-300 dark:border-gray-600 h-96 mb-4 w-full py-32"></div>
        <button @click="navigateToAccount"
            class="bg-gray-300 hover:bg-gray-400 text-gray-800 font-bold py-2 px-4 rounded inline-flex items-center">
            <svg class="fill-current w-4 h-4 mr-2" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
                <path d="M13 8V2H7v6H2l8 8 8-8h-5zM0 18h20v2H0v-2z" />
            </svg>
            <span>Download</span>
        </button>
    </main>
</template>

<script setup>
import { useRouter } from 'vue-router';

const router = useRouter();

const navigateToAccount = () => {
    router.push('/login/login'); // Navigate to the Account page
};
</script>

<style scoped></style>