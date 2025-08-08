<script setup lang="ts">
import { ref, onMounted } from 'vue'

const slides = [
  {
    image: new URL('../../assets/LandingPage_FirstImage.jpg', import.meta.url).href, // ← Remplace avec ton image AlloCoca
    title: 'Ton casier <br> Coca livré chez <br> toi, sans bouger.',
    button: 'Je commence ma commande',
    buttonLink: '#',
  },
  {
    image: new URL('../../assets/LandingPage_SecondImage.png', import.meta.url).href, // ← Image secondaire
    title: 'Ton pack d’eau <br> livré chez toi, <br> sans bouger.',
    button: 'Je commence ma commande',
    buttonLink: '#',
  },
]

const currentSlide = ref(0)

const nextSlide = () => {
  currentSlide.value = (currentSlide.value + 1) % slides.length
}

onMounted(() => {
  setInterval(() => {
    nextSlide()
  }, 5000) // Change toutes les 5 secondes
})
</script>

<template>
  <section class="relative w-full h-screen overflow-hidden">
    <!-- Slides -->
    <div
      class="flex transition-transform duration-1000 ease-in-out h-full"
      :style="{ transform: `translateX(-${currentSlide * 100}%)` }"
    >
      <div
        v-for="(slide, index) in slides"
        :key="index"
        class="w-full flex-shrink-0 h-full relative"
      >
        <img :src="slide.image" class="w-full h-full object-cover" alt="Slide image" />
        <div class="absolute inset-0 bg-black/40"></div>

        <!-- Text content -->
        <div
          class="absolute gap-8 inset-0 flex flex-col justify-center items-start px-8 md:px-20 text-white z-10"
        >
          <h1 v-html="slide.title" class="text-3xl md:text-[100px] font-bold w-[950px]"></h1>
          <a
            :href="slide.buttonLink"
            class="mt-6 gap-2.5 flex bg-red-600 hover:bg-red-700 text-white text-2xl font-semibold px-6 py-3 rounded-full shadow"
          >
            <span v-html="slide.button"></span>
            <svg
              width="40"
              height="30"
              viewBox="0 0 20 20"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M12.5001 9.16671L11.6667 16.6667M15.8334 9.16671L12.5001 3.33337M1.66675 9.16671H18.3334M2.91675 9.16671L4.25008 15.3334C4.328 15.7155 4.53745 16.0582 4.84199 16.3018C5.14652 16.5455 5.52684 16.6746 5.91675 16.6667H14.0834C14.4733 16.6746 14.8536 16.5455 15.1582 16.3018C15.4627 16.0582 15.6722 15.7155 15.7501 15.3334L17.1667 9.16671M3.75008 12.9167H16.2501M4.16675 9.16671L7.50008 3.33337M7.50008 9.16671L8.33342 16.6667"
                stroke="white"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>
          </a>
        </div>
      </div>
    </div>

    <!-- Overlay navbar space -->
    <div class="absolute top-0 left-0 w-full h-20 z-20"></div>
  </section>
</template>

<style scoped>
/* Aucun style custom requis ici */
</style>
