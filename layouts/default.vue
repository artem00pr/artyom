<template>
  <header class="flex flex-row w-full items-center relative bg-green-400 border-b-2 border-gray-400 max-sm:justify-between max-sm:relative">
    <div class="basis-1/4 max-sm:basis-auto justify-start px-8 min-w-40 max-sm:auto">
      <img src="assets/images/arizonalogo.png" class="w-16 h-16 bg-transparent">
    </div>
    <div class="basis-3/4 max-sm:basis-auto">
      <div :class="`basis-1/2 flex flex-row justify-end gap-x-4 !burger || burger`" class="max-sm:basis-auto max-sm:top-full max-sm:w-full max-sm:flex-col max-sm:gap-0 max-sm:hidden !burger">
        <NuxtLink to="/">Home</NuxtLink>
        <NuxtLink to="/Lab1" class="my-auto p-2 border-b-2 border-black hover:bg-gray-500 hover:text-white max-sm:w-full max-sm:text-center">Lab1</NuxtLink>
        <NuxtLink to="/Lab2" class="my-auto p-2 border-b-2 border-black hover:bg-gray-500 hover:text-white max-sm:w-full max-sm:text-center">Lab2</NuxtLink>
        <NuxtLink to="/Lab3" class="my-auto p-2 border-b-2 border-black hover:bg-gray-500 hover:text-white max-sm:w-full max-sm:text-center">Lab3</NuxtLink>
        <NuxtLink to="/Lab4" class="my-auto p-2 border-b-2 border-black hover:bg-gray-500 hover:text-white max-sm:w-full max-sm:text-center">Lab4</NuxtLink>
        <NuxtLink to="/Lab5" class="my-auto p-2 border-b-2 border-black hover:bg-gray-500 hover:text-white max-sm:w-full max-sm:text-center">Lab5</NuxtLink>
        <NuxtLink to="/Lab6" class="my-auto p-2 border-b-2 border-black hover:bg-gray-500 hover:text-white max-sm:w-full max-sm:text-center">Lab6</NuxtLink>
        <NuxtLink to="/login" class="my-auto p-2 border-b-2 border-black hover:bg-gray-500 hover:text-white max-sm:w-full max-sm:text-center">Login</NuxtLink>
        <NuxtLink to="/logout" class="my-auto p-2 border-b-2 border-black hover:bg-gray-500 hover:text-white max-sm:w-full max-sm:text-center">Logout</NuxtLink>
      </div>
      <div @click="switch_burger" class="max-sm:flex max-sm:flex-col max-sm:gap-1 max-sm:justify-between max-sm:items-center max-sm:w-8 max-sm:h-6">
        <span class="h-[3px] w-full bg-blue-950"></span>
        <span class="h-[3px] w-full bg-blue-950"></span>
        <span class="h-[3px] w-full bg-blue-950"></span>
      </div>
      <div v-else class="max-sm:flex-col max-sm:w-8 max-sm:h-6 justify-between max-sm:items-center max-sm:w-8 max-sm:h-6" @click="switch_burger">
        <span class="h-[3px] w-full bg-blue-950 rotate-45 relative top-[9px]"></span>
        <span class="h-[3px] w-full bg-blue-950 opacity-0"></span>
        <span class="h-[3px] w-full bg-blue-950 relative bottom-2 rotate-[-45deg]"></span>
      </div>
    </div>
  </header>

  <main class="p-5 flex bg-green-100 h-screen">
    <slot></slot>
  </main>

  <footer class="flex flex-row w-full bg-green-400 border-t-2 border-gray-400 items-center justify-center px-4 py-2 gap-4">
    <a href="https://www.youtube.com/" target="_blank">
      <img src="assets/images/youtube.png" class="w-16 h-16">
    </a>
    <a href="https://github.com/" target="_blank">
      <img src="assets/images/github.png" class="w-16 h-16">
    </a>
    <a href="https://www.facebook.com/" target="_blank">
      <img src="assets/images/facebook.png" class="w-16 h-16 bg-transparent">
    </a>
  </footer>
</template>
