<template>
  <section class="py-16 bg-white px-4 max-w-7xl mx-auto h-[665px]">
    <!-- Titre + bouton -->
    <div class="flex flex-col   lg:flex-row justify-center  items-start lg:items-center mb-12 gap-[630px]">
      <h2 class="text-3xl md:text-4xl font-bold text-black">Ce qu'en disent nos clients</h2>
      <button class="bg-red-500 hover:bg-red-600 text-white px-6 py-2 rounded-full transition">
        Je passe ma commande
      </button>
    </div>

    <!-- Liste dynamique des témoignages -->
     <div class="flex items-center justify-center">

       <div class="grid grid-cols-1 h-[300px]  w-[1300px] md:grid-cols-2 lg:grid-cols-3 gap-6">
         <div
           v-for="(testimonial, index) in testimonials"
           :key="index"
           class="bg-[#F9F9F9] rounded-lg p-6 text-center shadow-sm"
         >
           <div class="flex justify-center mb-2">
             <StarRating :count="5" />
           </div>
           <img
             :src="testimonial.image"
             :alt="testimonial.name"
             class="w-16 h-16 border border-gray-200 rounded-full mx-auto mb-4 object-cover"
           />
           <p class="text-gray-700 text-sm mb-2 whitespace-pre-line">
             {{ testimonial.message }}
           </p>
           <p class="font-bold text-black">{{ testimonial.name }}, {{ testimonial.city }}</p>
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
