<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import MainNavbar from './components/MainNavbar.vue'
import HeroSection from './components/HeroSection.vue'
import FeaturedProducts from './components/FeaturedProducts.vue'
import AboutUs from './components/AboutUs.vue'
import productsGrid from './components/ProductsGrid.vue'
</script>

<template>
  <MainNavbar />
  <HeroSection />
  <FeaturedProducts />
  <AboutUs />
  <productsGrid />
  <RouterView />
</template>

<style lang="scss">
@import "./scss/app.scss"
</style>
