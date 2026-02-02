<template>
  <div class="page">
    <h1>Gallery</h1>
    <p>A collection of moments.</p>
    
    <div class="gallery-grid">
      <div v-for="i in 6" :key="i" class="gallery-item">
        <div class="image-placeholder">
          <span>Photo {{ i }}</span>
        </div>
        <p class="caption">This is a short remark about photo {{ i }}.</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.page {
  max-width: 1000px;
  margin: 0 auto;
  padding: 2rem;
}

.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 2rem;
  margin-top: 2rem;
}

.image-placeholder {
  background-color: #2a2a2a;
  aspect-ratio: 4/3;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 4px;
  color: #666;
}

.caption {
  margin-top: 0.5rem;
  font-size: 0.9rem;
  opacity: 0.8;
}
</style>