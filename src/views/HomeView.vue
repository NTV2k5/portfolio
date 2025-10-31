<script setup>
import { ref, onMounted } from 'vue'
import axios from 'axios'

const profile = ref({})

onMounted(async () => {
  try {
    const response = await axios.get('http://localhost:3000/profile')
    profile.value = response.data
  } catch (error) {
    console.error('Error fetching profile:', error)
  }
})
</script>

<template>
  <section style="text-align: center; padding: 4rem 1rem; background: url('https://images.unsplash.com/photo-1506744038136-46273834b3fb?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80') no-repeat center center/cover; color: white; border-radius: 10px; box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);">
    <h2 style="font-size: 2.5rem; font-weight: 700; margin-bottom: 1.5rem; color: #1e3a8a; text-shadow: 1px 1px 4px rgba(0, 0, 0, 0.1); animation: fadeIn 1s ease-in;">Welcome to My Portfolio</h2>
    <p style="font-size: 1.3rem; color: #4b5563; max-width: 600px; margin: 0 auto; line-height: 1.6; animation: slideUp 1s ease-out 0.5s backwards;">{{ profile.bio || 'Loading...' }}</p>
  </section>
</template>

<style scoped>
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

@keyframes slideUp {
  from { transform: translateY(20px); opacity: 0; }
  to { transform: translateY(0); opacity: 1; }
}
</style>