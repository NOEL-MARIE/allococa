<script setup lang="ts">
// Pas besoin de script ici, footer statique
</script>

<template>
  <div class="bg-black">
    <footer class="bg-black max-w-7xl mx-auto text-white px-6 md:px-20 py-10 min-h-[440px]">
      <!-- Conteneur principal flex-col sur mobile, flex-row sur md+ -->
      <div class="flex flex-col justify-between gap-10 pb-16 border-b border-gray-800 md:flex-row md:pb-32">
        <!-- Colonne 1 : Logo + Description + Réseaux -->
        <div class="flex-1 max-w-xs space-y-4">
          <!-- Logo -->
          <img src="../assets/Logo Allo Cola.svg" alt="AlloCoca Logo" class="w-28" />

          <!-- Description -->
          <p class="text-sm text-gray-300">
            AlloCoca.ci - Ton service de livraison de boissons préféré à Abidjan. T'as soif ? Clique, on arrive.
          </p>

          <!-- Réseaux sociaux -->
          <div class="flex gap-6 mt-2 text-2xl">
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
          <h3 class="mb-3 text-sm text-gray-400 uppercase">Liens rapides</h3>
          <a href="#" class="text-sm text-white hover:text-gray-400">Comment ça marche</a>
          <a href="#" class="text-sm text-white hover:text-gray-400">Commander</a>
          <a href="#" class="text-sm text-white hover:text-gray-400">Contact</a>
        </div>

        <!-- Colonne 3 : Légal -->
        <div class="flex flex-col gap-3">
          <h3 class="mb-3 text-sm text-gray-400 uppercase">Légal</h3>
          <a href="#" class="text-sm text-white hover:text-gray-400">Mentions légales</a>
          <a href="#" class="text-sm text-white hover:text-gray-400">Politique de confidentialité</a>
          <a href="#" class="text-sm text-white hover:text-gray-400">CGV</a>
        </div>
      </div>

      <!-- Bas de page : colonne sur mobile, ligne sur md+ -->
      <div class="flex flex-col justify-between gap-2 mt-6 text-xs text-gray-500 md:flex-row md:gap-0">
        <p>© 2025 AlloCoca.ci - Tous droits réservés</p>
        <p>Website BY THEDESIGNHERO</p>
      </div>
    </footer>
  </div>
</template>

<style scoped>
/* Pas de styles particuliers nécessaires avec Tailwind pour la responsivité */
</style>
