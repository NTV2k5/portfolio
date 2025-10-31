<script setup>
import { RouterLink } from 'vue-router'
</script>

<template>
  <header style="background: linear-gradient(90deg, #2a5298, #1e3a8a); color: white; padding: 1.5rem 1rem; box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);">
    <nav style="max-width: 1200px; margin: 0 auto; display: flex; justify-content: space-between; align-items: center;">
      <h1 style="font-size: 1.8rem; font-weight: 700; letter-spacing: 1px;">Portfolio</h1>
      <ul style="display: flex; gap: 1.5rem; list-style: none; margin: 0; padding: 0;">
        <li><RouterLink to="/" class="nav-link">Home</RouterLink></li>
        <li><RouterLink to="/about" class="nav-link">About</RouterLink></li>
        <li><RouterLink to="/projects" class="nav-link">Projects</RouterLink></li>
        <li><RouterLink to="/skills" class="nav-link">Skills</RouterLink></li>
        <li><RouterLink to="/contact" class="nav-link">Contact</RouterLink></li>
      </ul>
    </nav>
  </header>
</template>

<style scoped>
.nav-link {
  text-decoration: none;
  color: white;
  font-size: 1.1rem;
  font-weight: 500;
  transition: color 0.3s ease, transform 0.2s ease;
}

.nav-link:hover {
  color: #bbf7d0;
  transform: translateY(-2px);
}
</style>