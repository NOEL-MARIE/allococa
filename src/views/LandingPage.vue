<template>
  <div>
    <Accueil />
    <ProductAvailable />
    <ComandType />
    <CallToAction />
    <HowItWorks />
    <WhyAlloCoca />
    <CustomerTestimonials />
  </div>
</template>
<script setup lang="ts">
import Accueil from '../components/LandingPage_Component/FirstSection.vue'
import ProductAvailable from '../components/LandingPage_Component/ProductAvailable.vue'
import ComandType from '../components/LandingPage_Component/ComandType.vue'
import CallToAction from '../components/LandingPage_Component/CallToAction.vue'
import HowItWorks from '../components/LandingPage_Component/HowItWorks.vue'
import WhyAlloCoca from '../components/LandingPage_Component/WhyAlloCoca.vue'
import CustomerTestimonials from '../components/LandingPage_Component/CustomerTestimonials.vue'
</script>
