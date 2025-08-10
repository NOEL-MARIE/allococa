<template>
  <header
    class="flex items-center justify-between w-full px-6 py-4 text-white bg-[#F11123] md:bg-transparent md:fixed md:top-0 md:left-0 md:z-50 sm:px-10 md:px-16"
  >
    <!-- Logo -->
    <div class="text-xl font-extrabold cursor-pointer select-none">
      <img src="../assets/Logo Allo Cola.svg" alt="Logo" class="h-8 md:h-10" />
    </div>

    <!-- Menu desktop -->
    <nav class="hidden space-x-8 text-sm font-semibold tracking-wide md:flex">
      <a href="#" class="text-xl hover:underline">Comment ça marche</a>
      <a href="#" class="text-xl hover:underline">Commander</a>
      <a href="#" class="text-xl hover:underline">Contactez-nous</a>
    </nav>

    <!-- Icone burger mobile -->
    <button
      @click="isMenuOpen = !isMenuOpen"
      aria-label="Menu"
      class="md:hidden p-2 rounded border border-white hover:bg-white hover:text-[#7C6E65] transition-colors"
    >
      <svg
        xmlns="http://www.w3.org/2000/svg"
        fill="none"
        stroke="currentColor"
        stroke-width="2"
        stroke-linecap="round"
        stroke-linejoin="round"
        class="w-6 h-6"
        viewBox="0 0 24 24"
      >
        <line x1="3" y1="12" x2="21" y2="12" />
        <line x1="3" y1="6" x2="21" y2="6" />
        <line x1="3" y1="18" x2="21" y2="18" />
      </svg>
    </button>

    <!-- Icone panier -->
    <button
      aria-label="Panier"
      class="p-2 rounded-full border cursor-pointer border-white hover:bg-white hover:text-[#7C6E65] transition-colors ml-4"
    >
      <svg
        xmlns="http://www.w3.org/2000/svg"
        fill="none"
        stroke="currentColor"
        stroke-width="2"
        stroke-linecap="round"
        stroke-linejoin="round"
        class="w-6 h-6"
        viewBox="0 0 24 24"
      >
        <circle cx="9" cy="21" r="1"></circle>
        <circle cx="20" cy="21" r="1"></circle>
        <path d="M1 1h4l2.68 13.39a1 1 0 0 0 .99.61h9.72a1 1 0 0 0 .98-.79l1.38-7.45H6"></path>
      </svg>
    </button>
  </header>

  <!-- Menu mobile déroulant -->
  <nav
    v-if="isMenuOpen"
    class="fixed left-0 right-0 z-40 flex flex-col px-6 py-6 space-y-4 text-white bg-black top-16 bg-opacity-70 backdrop-blur-md md:hidden"
  >
    <a href="#" class="text-lg hover:underline">Comment ça marche</a>
    <a href="#" class="text-lg hover:underline">Commander</a>
    <a href="#" class="text-lg hover:underline">Contactez-nous</a>
  </nav>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const isMenuOpen = ref(false)
</script>

<style scoped>
/* Rien de spécial ici, tout est géré via Tailwind */
</style>
