<script setup>
import { ref } from 'vue'

const form = ref({ name: '', email: '', message: '' })

const submitForm = () => {
  console.log('Form submitted:', form.value)
  alert('Message sent! (Mock)')
  form.value = { name: '', email: '', message: '' }
}
</script>

<template>
  <section style="padding: 4rem 1rem; max-width: 600px; margin: 0 auto;">
    <h2 style="font-size: 2rem; font-weight: 700; margin-bottom: 2rem; color: #1e3a8a; text-align: center;">Contact Me</h2>
    <form @submit.prevent="submitForm" style="display: flex; flex-direction: column; gap: 1.5rem; background-color: white; padding: 2rem; border-radius: 10px; box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);">
      <input v-model="form.name" placeholder="Name" style="border: 1px solid #d1d5db; padding: 0.75rem; border-radius: 5px; font-size: 1rem;" required />
      <input v-model="form.email" type="email" placeholder="Email" style="border: 1px solid #d1d5db; padding: 0.75rem; border-radius: 5px; font-size: 1rem;" required />
      <textarea v-model="form.message" placeholder="Message" style="border: 1px solid #d1d5db; padding: 0.75rem; border-radius: 5px; font-size: 1rem; resize: vertical; min-height: 100px;" required></textarea>
      <button type="submit" style="background: linear-gradient(90deg, #10b981, #059669); color: white; padding: 0.75rem; border-radius: 5px; border: none; font-size: 1rem; cursor: pointer; transition: transform 0.3s ease;">
        Send Message
      </button>
    </form>
  </section>
</template>

<style scoped>
button:hover {
  transform: translateY(-2px);
}
</style>