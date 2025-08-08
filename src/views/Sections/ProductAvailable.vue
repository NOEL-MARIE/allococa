<script setup lang="ts">
import cocaImage from '../../assets/coca.png'
import spriteImage from '../../assets/sprite.png'
import fantaImage from '../../assets/fanta.png'
import schweppesImage from '../../assets/schweppes.png'
import { ref } from 'vue'

type Product = {
  id: number
  name: string
  image: string
  price: number
  isNew: boolean
}

const tabs = [
  { name: 'Boissons gazeuse', key: 'gazeuse' },
  { name: 'Eaux minérales', key: 'eaux' },
]
const activeTab = ref('gazeuse')

const productsGazeuses: Product[] = [
  {
    id: 1,
    name: 'Coca-Cola Classique',
    image: cocaImage,
    price: 250,
    isNew: true,
  },
  {
    id: 2,
    name: 'Sprite',
    image: spriteImage,
    price: 250,
    isNew: true,
  },
  {
    id: 3,
    name: 'Fanta Orange',
    image: fantaImage,
    price: 250,
    isNew: false,
  },
  {
    id: 4,
    name: 'Schweppes Tonique',
    image: schweppesImage,
    price: 250,
    isNew: false,
  },
]

const productsEaux: Product[] = [...productsGazeuses] // À adapter plus tard

const casier = ref<Product[]>([])

function addToCasier(product: Product) {
  casier.value.push(product)
}

function getProducts() {
  return activeTab.value === 'gazeuse' ? productsGazeuses : productsEaux
}
</script>

<template>
  <section class="bg-white w-full py-16 px-4">
    <div class="max-w-7xl mx-auto flex flex-col h-full">

      <!-- Header + Description -->
      <div class="flex flex-col md:flex-row justify-between items-start pt-12">
        <h1 class="text-2xl md:text-5xl text-black font-bold mb-6 md:mb-0 w-full md:w-2/5">
          Nos produits disponibles
        </h1>
        <div class="w-full md:w-2/5 text-gray-700 md:ml-auto text-base md:text-2xl">
          <span>
            Compose ton casier comme tu veux ou choisis directement <br />
            un pack prêt à livrer. Des bouteilles fraîches, des prix fixes, <br />
            et la livraison offerte chez toi en 24h&nbsp;!
          </span>
          <div class="mt-2 flex gap-2.5 items-center">
            <a href="#" class="underline font-semibold text-black hover:text-gray-800 transition">
              Configurer mon casier
            </a>
            <svg
              width="20"
              height="20"
              viewBox="0 0 20 20"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M4.16675 9.99105H15.8334M15.8334 9.99105L10.0001 4.15771M15.8334 9.99105L10.0001 15.8244"
                stroke="black"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>
          </div>
        </div>
      </div>

      <!-- Onglets -->
      <div class="flex space-x-10 mt-12 border-b border-gray-200">
        <button
          v-for="tab in tabs"
          :key="tab.key"
          @click="activeTab = tab.key"
          :class="[
            'pb-2 text-lg font-medium duration-200 outline-none',
            activeTab === tab.key ? 'border-b-2 border-black text-black' : 'text-gray-500',
          ]"
        >
          {{ tab.name }}
        </button>
      </div>

      <!-- Grille produits -->
      <div class="mt-8 flex-1">
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
          <div
            v-for="product in getProducts()"
            :key="product.id"
            class="bg-gray-50 rounded-lg shadow-sm p-6 flex flex-col relative"
          >
            <span
              v-if="product.isNew"
              class="absolute top-4 left-4 bg-red-500 text-white text-xs px-3 py-1 rounded-full font-semibold"
            >
              Nouveauté
            </span>
            <img :src="product.image" :alt="product.name" class="h-72 mb-5 object-contain" />
            <div class="text-left w-full">
              <div class="text-gray-500 text-xl mb-1">Casier de 24 bouteilles</div>
              <div class="font-bold mb-1 text-black text-left">{{ product.name }}</div>
              <span class="text-xl text-gray-600 mb-1 block">30cl | {{ product.price }} FCFA</span>
            </div>
            <button
              class="mt-4 w-[103px] group flex items-center text-black justify-center py-2 px-4 bg-white border border-black rounded-full font-semibold hover:bg-black hover:text-white transition"
              @click="addToCasier(product)"
            >
              <span class="mr-2">
                <svg
                  width="20"
                  height="20"
                  viewBox="0 0 20 20"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M12.5001 9.15755L11.6667 16.6576M15.8334 9.15755L12.5001 3.32422M1.66675 9.15755H18.3334M2.91675 9.15755L4.25008 15.3242C4.328 15.7063 4.53745 16.049 4.84199 16.2927C5.14652 16.5363 5.52684 16.6654 5.91675 16.6576H14.0834C14.4733 16.6654 14.8536 16.5363 15.1582 16.2927C15.4627 16.049 15.6722 15.7063 15.7501 15.3242L17.1667 9.15755M3.75008 12.9076H16.2501M4.16675 9.15755L7.50008 3.32422M7.50008 9.15755L8.33342 16.6576"
                    class="stroke-black group-hover:stroke-white transition duration-300"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                </svg>
              </span>
              Casier
            </button>
            <button
              class="absolute bottom-6 right-6 rounded-full border border-black p-2 hover:bg-gray-200 hover:cursor-pointer transition"
              aria-label="Voir plus"
            >
              <svg
                width="20"
                height="20"
                viewBox="0 0 20 20"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  d="M4.16675 9.99105H15.8334M15.8334 9.99105L10.0001 4.15771M15.8334 9.99105L10.0001 15.8244"
                  stroke="black"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                />
              </svg>
            </button>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>
