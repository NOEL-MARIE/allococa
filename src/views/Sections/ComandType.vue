<script setup lang="ts">
import { ref } from 'vue'
import ImageCeleste from '../../assets/ImageCeleste.png'
import ImageCoca_Casier from '../../assets/ImageCoca_Casier.png'
import ImageBouteille_Gazeuse from '../../assets/ImageBouteille_Gazeuse.png'

type OrderType = {
  id: number
  title: string
  description: string
  callToAction: string
  imgSrc: string
  ctaLink: string
}

const orders = ref<OrderType[]>([
  {
    id: 1,
    title: 'Casiers complets',
    description:
      'Choisis directement un casier pré-rempli (24 bouteilles) : Coca-Cola, Fanta, Sprite...',
    callToAction: 'Voir les casiers',
    imgSrc: ImageCoca_Casier,
    ctaLink: '#',
  },
  {
    id: 2,
    title: 'Casiers à composer',
    description:
      'Compose ton casier bouteille par bouteille. Tu choisis ce que tu veux, comme tu veux.',
    callToAction: 'Composer mon casier',
    imgSrc: ImageBouteille_Gazeuse,
    ctaLink: '#',
  },
  {
    id: 3,
    title: "Packs d'eau",
    description: "Commandes en pack d'eaux (Céleste, Cristalline, Awa)",
    callToAction: "Voir les pack d'eau",
    imgSrc: ImageCeleste,
    ctaLink: '#',
  },
])
</script>

<template>
  <div class="flex h-[825px] w-screen items-center justify-center bg-white p-4 md:p-0">
    <section class="w-full max-w-7xl mx-auto px-2 sm:px-4 py-8 md:py-12">
      <h2 class="text-center text-3xl sm:text-4xl md:text-5xl font-bold mb-2 text-black">
        Vos type de commande
      </h2>
      <p class="text-center text-base sm:text-xl md:text-2xl mb-10 text-black max-w-3xl mx-auto">
        Trois façons simples de commander tes boissons préférées
      </p>

      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
        <article
          v-for="order in orders"
          :key="order.id"
          class="rounded-3xl overflow-hidden shadow-lg flex flex-col"
        >
          <img
            :src="order.imgSrc"
            :alt="order.title"
            class="w-full h-[200px] sm:h-[280px] md:h-[357px] object-cover"
            loading="lazy"
          />
          <div class="bg-red-600 text-white p-4 sm:p-5 flex flex-col justify-between flex-1">
            <h3 class="text-base sm:text-lg font-bold mb-2">
              {{ order.title }}
            </h3>
            <p class="text-xs sm:text-sm mb-4 leading-relaxed">
              {{ order.description }}
            </p>
            <a
              :href="order.ctaLink"
              class="inline-block text-white underline font-semibold mt-3 hover:text-red-200 transition"
            >
              {{ order.callToAction }} &rarr;
            </a>
          </div>
        </article>
      </div>
    </section>
  </div>
</template>
