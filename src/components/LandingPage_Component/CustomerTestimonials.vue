<template>
  <section class="py-16 bg-white px-4 max-w-7xl mx-auto min-h-[665px]">

    <!-- Titre + bouton -->
    <div
      class="flex flex-col items-start justify-between gap-6 mb-12 lg:flex-row lg:items-center"
    >
      <h2 class="text-3xl font-bold text-black md:text-4xl">
        Ce qu'en disent nos clients
      </h2>
      <button
        class="px-6 py-2 mt-4 text-white transition bg-red-500 rounded-full lg:mt-0 hover:bg-red-600 whitespace-nowrap"
      >
        Je passe ma commande
      </button>
    </div>

    <!-- Liste dynamique des témoignages -->
    <div class="flex justify-center">
      <div
        class="grid grid-cols-1 gap-6 w-full max-w-[1300px]
               h-auto md:grid-cols-2 lg:grid-cols-3"
      >
        <div
          v-for="(testimonial, index) in testimonials"
          :key="index"
          class="bg-[#F9F9F9] rounded-lg p-6 text-center shadow-sm flex flex-col items-center"
        >
          <div class="flex justify-center mb-2">
            <StarRating :count="5" />
          </div>
          <img
            :src="testimonial.image"
            :alt="testimonial.name"
            class="object-cover w-16 h-16 mb-4 border border-gray-200 rounded-full"
            loading="lazy"
          />
          <p class="mb-2 text-sm leading-relaxed text-gray-700 whitespace-pre-line">
            {{ testimonial.message }}
          </p>
          <p class="text-sm font-bold text-black md:text-base">
            {{ testimonial.name }}, {{ testimonial.city }}
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import StarRating from '../../components/StarRating.vue'

interface Testimonial {
  name: string
  city: string
  message: string
  image: string
}

const testimonials: Testimonial[] = [
  {
    name: 'Fatou B.',
    city: 'Yopougon',
    message: `J’ai reçu mon casier en moins de 2h !\nTrès pratique pour mes soirées entre amis.`,
    image: new URL('@/assets/TESTIMONIAL_IMAGE_1 (1).png', import.meta.url).href,
  },
  {
    name: 'Kouassi M.',
    city: 'Cocody',
    message: `C’est trop cool de pouvoir mélanger Coca, Fanta\net Sprite dans le même casier !`,
    image: new URL('@/assets/TESTIMONIAL_IMAGE_1 (2).png', import.meta.url).href,
  },
  {
    name: 'Aya K.',
    city: 'Marcory',
    message: `Service client au top sur WhatsApp. Ils ont\nremplacé une bouteille abîmée le jour même !`,
    image: new URL('@/assets/TESTIMONIAL_IMAGE_1 (3).png', import.meta.url).href,
  },
]
</script>

<style scoped>
/* Aucun style personnalisé requis : tout est géré par Tailwind */
</style>
