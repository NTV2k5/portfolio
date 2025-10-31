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
  <section style="padding: 4rem 1rem; background-color: white; border-radius: 10px; box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05); max-width: 800px; margin: 2rem auto;">
    <h2 style="font-size: 2rem; font-weight: 700; margin-bottom: 1.5rem; color: #1e3a8a;">About Me</h2>
    <div style="display: flex; align-items: center; gap: 2rem;">
      <div style="flex: 1; text-align: center;">
        <p style="font-size: 1.2rem; color: #4b5563;">{{ profile.name || 'Loading...' }} - <span style="color: #2a5298;">{{ profile.title || '' }}</span></p>
        <p style="margin-top: 1rem; font-size: 1rem; color: #6b7280; line-height: 1.6;">{{ profile.bio || 'Loading...' }}</p>
      </div>
    </div>
  </section>
</template>