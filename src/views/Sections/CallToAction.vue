<script setup lang="ts">
import Cta_Image from '../../assets/Cta_Image.png';

function startOrderWithoutAccount() {
  // Logique démarrage commande sans compte
  alert('Commencer la commande sans compte');
}

function findOrder() {
  // Logique de recherche de commande
  alert('Retrouver une commande');
}
</script>

<template>
  <section
    class="w-full h-[800px]  bg-black flex items-center justify-center px-4 py-12 md:py-24"
  >
    <div
      class="w-full max-w-7xl mx-auto grid grid-cols-1 md:grid-cols-2 gap-10 items-center"
    >
      <!-- Texte gauche -->
      <div class="text-white max-w-lg mx-auto md:mx-0">
        <h2 class="text-3xl md:text-6xl font-bold mb-9 ">
          Pas besoin de<br />créer un compte !
        </h2>
        <p class="text-gray-300 mb-12 text-sm font-light md:text-2xl">
          Pas envie de perdre du temps ? Commence ta commande en 1 clic, on prendra tes infos plus tard.
        </p>

        <div class="flex flex-col space-y-9 text-sm md:text-base">
          <button
            @click="startOrderWithoutAccount"
            class="inline-flex items-center text-xl font-semibold underline text-white hover:text-gray-300 transition focus:outline-none"
          >
            Commence sans Compte
            <svg
              class="ml-2 w-4 h-4 stroke-current"
              fill="none"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
              viewBox="0 0 24 24"
              aria-hidden="true"
              focusable="false"
            >
              <path d="M5 12h14M13 6l6 6-6 6" />
            </svg>
          </button>

          <button
            @click="findOrder"
            class="inline-flex items-center text-xl font-semibold underline text-white hover:text-gray-300 transition focus:outline-none"
          >
            Retrouvez une commande
            <svg
              class="ml-2 w-4 h-4 stroke-current"
              fill="none"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
              viewBox="0 0 24 24"
              aria-hidden="true"
              focusable="false"
            >
              <path d="M5 12h14M13 6l6 6-6 6" />
            </svg>
          </button>
        </div>
      </div>

      <!-- Image droite -->
      <div class="w-full max-w-md mx-auto md:max-w-none">
        <img
          :src="Cta_Image"
          alt="Personnes partageant un repas"
          class="rounded-lg shadow-lg object-cover w-full h-full max-h-[800px]"
          loading="lazy"
        />
      </div>
    </div>
  </section>
</template>
