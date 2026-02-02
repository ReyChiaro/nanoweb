<script setup lang="ts">
// import { useRouter } from 'vue-router'
</script>

<template>
  <div class="home">
    <h1>Welcome.</h1>
    <p class="subtitle">Minimalist. Professional. Focused.</p>
    
    <nav class="home-nav">
      <router-link to="/blog">Blog</router-link>
      <router-link to="/projects">Projects</router-link>
      <router-link to="/gallery">Gallery</router-link>
      <router-link to="/about">About</router-link>
    </nav>
  </div>
</template>

<style scoped>
.home {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 80vh;
  text-align: center;
}

h1 {
  font-size: 3rem;
  margin-bottom: 0.5rem;
  font-weight: 700;
}

.subtitle {
  font-size: 1.2rem;
  opacity: 0.8;
  margin-bottom: 2rem;
}

.home-nav {
  display: flex;
  gap: 1.5rem;
}

.home-nav a {
  text-decoration: none;
  font-weight: 500;
  border-bottom: 1px solid transparent;
  transition: border-color 0.2s;
}

.home-nav a:hover {
  border-color: currentColor;
}
</style>