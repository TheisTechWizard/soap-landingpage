<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import MainNavbar from './components/MainNavbar.vue'
import HeroSection from './components/HeroSection.vue'
import FeaturedProducts from './components/FeaturedProducts.vue'
import AboutUs from './components/AboutUs.vue'
import ProductsGrid from './components/ProductsGrid.vue'
import BenefitsSection from './components/BenefitsSection.vue'
import CreatorSection from './components/CreatorSection.vue'

</script>

<template>
  <MainNavbar />
  <HeroSection />
  <FeaturedProducts />
  <AboutUs />
  <ProductsGrid />
  <BenefitsSection />
  <CreatorSection />
  <RouterView />
</template>

<style lang="scss">
@import "./scss/app.scss"
</style>
