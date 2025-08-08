<template>
  <header
    class="bg-[#7C6E65] text-white px-6 sm:px-10 md:px-16 py-4 flex items-center justify-between"
  >
    <!-- Logo -->
    <div class="text-xl font-extrabold cursor-pointer select-none">
      <img src="../assets/Logo Allo Cola.svg" alt="" />
    </div>

    <!-- Menu -->
    <nav class="hidden md:flex space-x-8 text-sm font-semibold tracking-wide">
      <a href="#" class="hover:underline text-xl">Comment ça marche</a>
      <a href="#" class="hover:underline text-xl">Commander</a>
      <a href="#" class="hover:underline text-xl">Contactez-nous</a>
    </nav>

    <!-- Cart Icon -->
    <button
      aria-label="Panier"
      class="p-2 rounded-full border cursor-pointer border-white hover:bg-white hover:text-[#7C6E65] transition-colors"
    >
      <svg
        xmlns="http://www.w3.org/2000/svg"
        fill="none"
        stroke="currentColor"
        stroke-width="2"
        stroke-linecap="round"
        stroke-linejoin="round"
        class="w-6 h-6 hover:cursour-pointer"
        viewBox="0 0 24 24"
      >
        <circle cx="9" cy="21" r="1"></circle>
        <circle cx="20" cy="21" r="1"></circle>
        <path d="M1 1h4l2.68 13.39a1 1 0 0 0 .99.61h9.72a1 1 0 0 0 .98-.79l1.38-7.45H6"></path>
      </svg>
    </button>
  </header>
</template>

<script setup lang="ts">
// Pas de script nécessaire, tout est statique
</script>
