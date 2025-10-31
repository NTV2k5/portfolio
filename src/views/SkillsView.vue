<script setup>
import { ref, onMounted } from 'vue'
import axios from 'axios'

const skills = ref([])

onMounted(async () => {
  try {
    const response = await axios.get('http://localhost:3000/skills')
    skills.value = response.data
  } catch (error) {
    console.error('Error fetching skills:', error)
  }
})
</script>

<template>
  <section style="padding: 4rem 1rem; background-color: #f9fafb; border-radius: 10px; box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05); max-width: 800px; margin: 2rem auto;">
    <h2 style="font-size: 2rem; font-weight: 700; margin-bottom: 2rem; color: #1e3a8a; text-align: center;">My Skills</h2>
    <ul style="list-style-type: none; padding: 0; display: grid; gap: 1rem;">
      <li v-for="skill in skills" :key="skill.id" style="font-size: 1.1rem; color: #4b5563; padding: 0.75rem 1rem; background-color: white; border-radius: 5px; box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);">
        {{ skill.name }} - <span style="color: #10b981;">{{ skill.level }}</span>
      </li>
    </ul>
  </section>
</template>