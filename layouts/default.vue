<template>
  <header class="flex items-center justify-between w-full bg-green-400 border-b-2 border-gray-400 p-4">
    <div class="basis-1/4">
      <img src="assets/images/arizona.png" class="w-16 h-16 bg-transparent">
    </div>

    <div class="md:hidden" @click="toggleMobileMenu">
      <svg v-if="!mobileMenuOpen" class="w-8 h-8" fill="none" viewBox="0 0 24 24" stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
      </svg>
      <svg v-else class="w-8 h-8" fill="none" viewBox="0 0 24 24" stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
      </svg>
    </div>

    <nav :class="['flex-col md:flex-row md:flex gap-8 items-center', mobileMenuOpen ? 'flex' : 'hidden', 'md:block']">
      <NuxtLink to="/" class="p-2 hover:bg-gray-500 hover:text-white">
        Home
      </NuxtLink>

      <div class="relative p-2 hover:bg-gray-500 hover:text-white" @mouseenter="showSubmenu = true" @mouseleave="showSubmenu = false">
        Labs
        <div v-show="showSubmenu" class="absolute top-full left-0 bg-white text-black w-40 shadow-md">
          <NuxtLink to="/lab3" class="block p-2 border-b hover:bg-gray-500 hover:text-white">Lab3</NuxtLink>
          <NuxtLink to="/lab4" class="block p-2 border-b hover:bg-gray-500 hover:text-white">Lab4</NuxtLink>
          <NuxtLink to="/lab5" class="block p-2 border-b hover:bg-gray-500 hover:text-white">Lab5</NuxtLink>
          <NuxtLink to="/lab6" class="block p-2 hover:bg-gray-500 hover:text-white">Lab6</NuxtLink>
        </div>
      </div>

      <NuxtLink to="/login" class="p-2 hover:bg-gray-500 hover:text-white">
        LogIn
      </NuxtLink>
      <NuxtLink to="/logout" class="p-2 hover:bg-gray-500 hover:text-white">
        LogOut
      </NuxtLink>
    </nav>
  </header>

  <main class="p-5 flex bg-green-100 h-screen">
    <slot />
  </main>

  <footer class="flex flex-row w-full bg-green-400 border-t-2 border-gray-400 items-center justify-center p-4 gap-4">
    <a href="https://www.youtube.com/"><img src="assets/images/youtube.png" class="w-16 h-16"></a>
    <a href="https://github.com/"><img src="assets/images/github.png" class="w-16 h-16"></a>
    <a href="https://www.facebook.com/"><img src="assets/images/facebook.png" class="w-16 h-16 bg-transparent"></a>
  </footer>
</template>

<script setup>
import { ref } from 'vue';

const showSubmenu = ref(false);
const mobileMenuOpen = ref(false);

function toggleMobileMenu() {
  mobileMenuOpen.value = !mobileMenuOpen.value;
}
</script>

<style scoped>
nav {
  transition: all 0.3s ease;
}
</style>
