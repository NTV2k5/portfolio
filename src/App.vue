<script setup>
import AppHeader from './components/TheHeader.vue'
import AppFooter from './components/TheFooter.vue'
import { RouterView } from 'vue-router'
</script>

<template>
  <div style="min-height: 100vh; background: linear-gradient(135deg, #f0f4f8, #d9e2f3); font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;">
    <AppHeader />
    <main style="max-width: 1200px; margin: 0 auto; padding: 2rem 1rem;">
      <RouterView />
    </main>
    <AppFooter />
  </div>
</template>