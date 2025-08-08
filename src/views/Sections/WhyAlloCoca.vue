<template>
  <section class="bg-black text-white py-20 px-4">
    <div class="max-w-7xl mx-auto space-y-12">

      <!-- Titre -->
      <div class="text-center space-y-4">
        <h2 class="text-3xl md:text-4xl font-bold">Pourquoi choisir AlloCoca ?</h2>
        <p class="text-gray-300">La solution la plus simple pour tes boissons</p>
      </div>

      <!-- Avantages -->
      <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
        <div
          v-for="(feature, index) in features"
          :key="index"
          class="bg-white text-black rounded-xl p-6 flex items-start space-x-4"
        >
          <div class="text-2xl mt-1">
            <component :is="feature.icon" class="w-6 h-6 text-black" />
          </div>
          <div>
            <h3 class="font-semibold mb-1">{{ feature.title }}</h3>
            <p class="text-gray-600 text-sm">{{ feature.description }}</p>
          </div>
        </div>
      </div>

      <!-- Call to Action -->
      <div class="bg-white text-center rounded-xl p-8">
        <h3 class="text-xl md:text-2xl font-bold text-black mb-2">
          Prêt à passer ta première commande ?
        </h3>
        <p class="text-gray-600 mb-6">
          Rejoins des milliers de clients satisfaits à Abidjan
        </p>
        <div class="flex flex-col sm:flex-row justify-center items-center gap-4">
          <button class="bg-red-500 hover:bg-red-600 text-white px-6 py-2 rounded-full transition">
            Commander maintenant
          </button>
          <button class="border border-black text-black px-6 py-2 rounded-full hover:bg-gray-100 transition">
            Contacter via Whatsapp
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { Truck, ShieldCheck, RefreshCw, MessageCircle } from 'lucide-vue-next'

interface Feature {
  title: string
  description: string
  icon: unknown
}

const features: Feature[] = [
  {
    title: 'Livraison gratuite à Abidjan',
    description: 'Aucun frais de livraison, où que tu sois dans la capitale',
    icon: Truck,
  },
  {
    title: 'Paiement simple et sécurisé',
    description: 'Mobile Money accepté, transactions 100% sécurisées',
    icon: ShieldCheck,
  },
  {
    title: 'Casiers consignés, rechargeables',
    description: 'Système écologique, tu paies la consigne une seule fois',
    icon: RefreshCw,
  },
  {
    title: 'Assistance WhatsApp en 1 clic',
    description: 'Une question ? Notre équipe répond instantanément',
    icon: MessageCircle,
  },
]
</script>
