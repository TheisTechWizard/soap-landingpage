<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import MainNavbar from './components/MainNavbar.vue'
import HeroSection from './components/HeroSection.vue'
import FeaturedProducts from './components/FeaturedProducts.vue'
</script>

<template>
  <MainNavbar />
  <HeroSection />
  <FeaturedProducts />
  <RouterView />
</template>

<style lang="scss">
@import "./scss/app.scss"
</style>
