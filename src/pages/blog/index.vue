<script setup lang="ts">
import { computed } from 'vue'

// Import all markdown files in this directory
const modules = import.meta.glob('./*.md', { eager: true })

const posts = computed(() => {
  return Object.entries(modules).map(([path, mod]: [string, any]) => {
    const frontmatter = mod.frontmatter || {}
    // path is usually "./hello-world.md", we want "/blog/hello-world"
    // But since we are in pages/blog, the route is /blog/filename
    const slug = path.replace(/^\.\/(.*)\.md$/, '$1')
    return {
      path: `/blog/${slug}`,
      title: frontmatter.title || slug,
      date: frontmatter.date || 'No date',
      ...frontmatter
    }
  }).sort((a, b) => new Date(b.date).getTime() - new Date(a.date).getTime())
})
</script>

<template>
  <div class="page">
    <h1>Blog</h1>
    <ul class="post-list">
      <li v-for="post in posts" :key="post.path" class="post-item">
        <span class="date">{{ new Date(post.date).toLocaleDateString() }}</span>
        <router-link :to="post.path" class="title">{{ post.title }}</router-link>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.page {
  max-width: 800px;
  margin: 0 auto;
  padding: 2rem;
}

.post-list {
  list-style: none;
  padding: 0;
  margin-top: 2rem;
}

.post-item {
  display: flex;
  align-items: baseline;
  gap: 1rem;
  margin-bottom: 1rem;
}

.date {
  opacity: 0.6;
  font-size: 0.9rem;
  min-width: 100px;
}

.title {
  font-size: 1.2rem;
  text-decoration: none;
  color: inherit;
}

.title:hover {
  text-decoration: underline;
}
</style>