<template>
  <div class="min-h-screen flex flex-col bg-gradient-to-b from-rose-50 via-white to-blue-50 text-gray-800 font-sans transition-all">
    
    <header class="flex justify-between items-center px-8 py-4 bg-white/80 backdrop-blur-md shadow-sm border-b border-rose-100 max-sm:flex-col max-sm:items-start">
      <div class="flex items-center justify-between w-full sm:w-auto">
        <img src="assets/img/logo_ava.png" alt="Logo" class="w-14 h-14 rounded-full shadow-sm hover:scale-105 transition" />
        
        <div class="sm:hidden cursor-pointer" @click="switchBurger">
          <div v-if="!burger">
            <span class="block w-6 h-0.5 bg-gray-200 mb-1"></span>
            <span class="block w-6 h-0.5 bg-gray-700 mb-1"></span>
            <span class="block w-6 h-0.5 bg-gray-700"></span>
          </div>
          <div v-else>
            <span class="block w-6 h-0.5 bg-gray-700 rotate-45 translate-y-1.5"></span>
            <span class="block w-6 h-0.5 bg-gray-700 -rotate-45 -translate-y-1.5"></span>
          </div>
        </div>
      </div>

      
      <nav class="hidden sm:flex gap-6 items-center">
        <NuxtLink to="/" class="nav-link">Home</NuxtLink>
        <div class="relative">
          <NuxtLink to="#" @click.prevent="toggleLabs" class="nav-link">Labs ▾</NuxtLink>
          <ul v-show="labsOpen" class="absolute bg-white rounded-xl shadow-lg mt-2 border border-rose-100 z-20">
            <li><NuxtLink to="/Lab4" class="dropdown-item">Lab 4</NuxtLink></li>
            <li><NuxtLink to="/Lab5" class="dropdown-item">Lab 5</NuxtLink></li>
            <li><NuxtLink to="/Lab6" class="dropdown-item">Lab 6</NuxtLink></li>
          </ul>
        </div>
        <NuxtLink to="/login" class="nav-link">Log In</NuxtLink>
        <NuxtLink to="/logout" class="nav-link">Log Out</NuxtLink>
      </nav>
    </header>

    
    <transition name="fade">
      <nav v-show="burger" class="flex flex-col bg-white/80 backdrop-blur-sm border-t border-rose-100 sm:hidden">
        <NuxtLink to="/" class="mobile-link">Home</NuxtLink>
        <NuxtLink to="#" @click.prevent="toggleLabs" class="mobile-link">Labs</NuxtLink>
        <ul v-show="labsOpen" class="bg-rose-50/40 border-t border-rose-100">
          <li><NuxtLink to="/Lab4" class="mobile-dropdown">Lab 4</NuxtLink></li>
          <li><NuxtLink to="/Lab5" class="mobile-dropdown">Lab 5</NuxtLink></li>
          <li><NuxtLink to="/Lab6" class="mobile-dropdown">Lab 6</NuxtLink></li>
        </ul>
        <NuxtLink to="/login" class="mobile-link">Log In</NuxtLink>
        <NuxtLink to="/logout" class="mobile-link">Log Out</NuxtLink>
      </nav>
    </transition>

    
    <main class="flex-grow p-8 max-sm:p-4">
      <slot />
    </main>

    
    <footer class="flex justify-center items-center gap-6 bg-white/80 border-t border-rose-100 py-4 text-sm text-gray-500">
        <!-- Google -->
        <a href="https://www.google.com" target="_blank" class="transition hover:scale-110">
          <img src="https://www.svgrepo.com/show/475656/google-color.svg" class="w-6 h-6 drop-shadow" alt="Google logo" />
        </a>

        <!-- GitHub -->
        <a href="https://github.com" target="_blank" class="transition hover:scale-110">
          <img src="https://www.svgrepo.com/show/512317/github-142.svg" class="w-6 h-6 drop-shadow" alt="GitHub logo" />
        </a>

        <!-- YouTube -->
        <a href="https://www.youtube.com" target="_blank" class="transition hover:scale-110">
          <img src="https://netlify.com/favicon.ico" class="w-6 h-6 drop-shadow" alt="YouTube logo" />
        </a>
</footer>

  </div>
</template>

<script setup>
import { ref } from 'vue'

const labsOpen = ref(false)
const burger = ref(false)

const toggleLabs = () => {
  labsOpen.value = !labsOpen.value
}

const switchBurger = () => {
  burger.value = !burger.value
}

useHead({
  script: [
    {
      src: "https://www.googletagmanager.com/gtag/js?id=G-CXQNXLFMHP",
      async: true
    },
    {
      children: `
        window.dataLayer = window.dataLayer || [];
        function gtag(){dataLayer.push(arguments);}
        gtag('js', new Date());
        gtag('config', 'G-CXQNXLFMHP');
      `,
      type: "text/javascript"
    }
  ]
})
</script>




