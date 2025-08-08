<!-- src/components/Footer.vue -->
<script setup lang="ts">
</script>

<template>
  <div class="bg-black">

    <footer class="bg-black max-w-7xl mx-auto text-white px-6 md:px-20 h-[440px] py-10">
      <div class="flex flex-col md:flex-row justify-between gap-10 border-b border-gray-800 pb-32">
        <!-- Colonne 1 : Logo + Description + Réseaux -->
        <div class="flex-1 space-y-4">
          <!-- Logo -->
          <img src="../assets//Logo Allo Cola.svg" alt="AlloCoca Logo" class="w-28" />

          <!-- Description -->
          <p class="text-sm text-gray-300 max-w-xs">
            AlloCoca.ci - Ton service de livraison de boissons préféré à Abidjan. T'as soif ? Clique, on arrive.
          </p>

          <!-- Réseaux sociaux -->
          <div class="flex gap-4 text-xl mt-2">
            <a href="#" aria-label="TikTok" class="hover:text-gray-400">
              <i class="fab fa-tiktok"></i>
            </a>
            <a href="#" aria-label="Facebook" class="hover:text-gray-400">
              <i class="fab fa-facebook-f"></i>
            </a>
            <a href="#" aria-label="Instagram" class="hover:text-gray-400">
              <i class="fab fa-instagram"></i>
            </a>
          </div>
        </div>

        <!-- Colonne 2 : Liens rapides -->
        <div class="flex flex-col gap-3">
          <h3 class="text-sm text-gray-400 uppercase">Liens rapides</h3>
          <a href="#" class="text-white hover:text-gray-400 text-sm">Comment ça marche</a>
          <a href="#" class="text-white hover:text-gray-400 text-sm">Commander</a>
          <a href="#" class="text-white hover:text-gray-400 text-sm">Contact</a>
        </div>

        <!-- Colonne 3 : Légal -->
        <div class="flex flex-col gap-3">
          <h3 class="text-sm text-gray-400 uppercase">Légal</h3>
          <a href="#" class="text-white hover:text-gray-400 text-sm">Mentions légales</a>
          <a href="#" class="text-white hover:text-gray-400 text-sm">Politique de confidentialité</a>
          <a href="#" class="text-white hover:text-gray-400 text-sm">CGV</a>
        </div>
      </div>

      <!-- Bas de page -->
      <div class="mt-6 flex flex-col md:flex-row justify-between text-xs text-gray-500">
        <p>© 2025 AlloCoca.ci - Tous droits réservés</p>
        <p>Website BY THEDESIGNHERO</p>
      </div>
    </footer>
  </div>
</template>

<style scoped>
/* Tu peux ajouter des styles si besoin */
</style>
