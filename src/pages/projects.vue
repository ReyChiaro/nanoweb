<template>
  <div class="page">
    <h1>Projects</h1>
    <div class="project-grid">
      <div v-for="i in 4" :key="i" class="project-card">
        <h3>Project {{ i }}</h3>
        <p>A brief description of this amazing project. It solves X problem using Y technology.</p>
        <div class="links">
          <a href="#">Code</a>
          <a href="#">Demo</a>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.page {
  max-width: 800px;
  margin: 0 auto;
  padding: 2rem;
}

.project-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
  margin-top: 2rem;
}

.project-card {
  border: 1px solid var(--border-color, #333);
  padding: 1.5rem;
  border-radius: 8px;
  transition: transform 0.2s;
}

.project-card:hover {
  transform: translateY(-2px);
}

.links {
  margin-top: 1rem;
  display: flex;
  gap: 1rem;
}
</style>