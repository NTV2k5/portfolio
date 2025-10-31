<script setup>
import { ref, onMounted } from 'vue'
import axios from 'axios'

const projects = ref([])

onMounted(async () => {
  try {
    const response = await axios.get('http://localhost:3000/projects')
    projects.value = response.data
  } catch (error) {
    console.error('Error fetching projects:', error)
  }
})
</script>

<template>
  <section style="padding: 4rem 1rem;">
    <h2 style="font-size: 2rem; font-weight: 700; margin-bottom: 2rem; color: #1e3a8a; text-align: center;">My Projects</h2>
    <div style="display: grid; grid-template-columns: 1fr; gap: 1.5rem; max-width: 1200px; margin: 0 auto;">
      <div v-for="project in projects" :key="project.id" style="background-color: white; padding: 1.5rem; border-radius: 10px; box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1); transition: transform 0.3s ease;">
        <h3 style="font-size: 1.3rem; font-weight: 600; margin-bottom: 0.5rem; color: #2a5298;">{{ project.title }}</h3>
        <p style="font-size: 1rem; color: #6b7280; margin-bottom: 1rem;">{{ project.description }}</p>
        <a :href="project.link" target="_blank" style="color: #10b981; text-decoration: none; font-weight: 500;">View Project</a>
      </div>
      <p v-if="!projects.length" style="font-size: 1rem; color: #6b7280; text-align: center;">Loading projects...</p>
    </div>
  </section>
</template>

<style scoped>
div {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1.5rem;
}

@media (min-width: 768px) {
  div {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  div {
    grid-template-columns: repeat(3, 1fr);
  }
}

div > div:hover {
  transform: translateY(-5px);
}

a:hover {
  text-decoration: underline;
}
</style>