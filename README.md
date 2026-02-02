# Personal Portfolio

A minimalist, professional portfolio website built with Vue 3, Vite, and TypeScript.

## Features

*   **Dark Mode:** Minimalist design focused on content.
*   **Blog Engine:** "Hexo-like" blogging. Write Markdown files in `src/pages/blog/*.md` and they automatically appear in the blog list.
*   **Gallery:** Grid layout for photography.
*   **Projects:** Showcase your work.
*   **Auto-Deployment:** configured for GitHub Pages.

## How to use

### 1. Install Dependencies
```bash
npm install
```

### 2. Development
```bash
npm run dev
```
Visit `http://localhost:5173`.

### 3. Add a Blog Post
Create a new file in `src/pages/blog/my-new-post.md`:

```markdown
---
title: My New Post
date: 2023-10-27
---

# Title

Content goes here...
```

It will automatically be listed at `/blog`.

### 4. Deployment
Push to the `main` branch. The GitHub Action will automatically build and deploy to the `gh-pages` branch.
*Note: Ensure GitHub Pages is enabled in your repository settings and set to serve from the `gh-pages` branch.*