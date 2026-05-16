<template>
  <div class="links-container">
    <div v-for="category in linksData.categories" :key="category.title" class="category-block">
      <h2 class="category-title">{{ category.title }}</h2>
      <div class="links-grid">
        <a
          v-for="item in category.items"
          :key="item.name"
          :href="item.url"
          target="_blank"
          rel="noopener noreferrer"
          class="link-item"
        >
          {{ item.name }}
        </a>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
// @ts-ignore
import linksData from "../data/links";
</script>

<style scoped>
.links-container {
  padding: 20px;
  max-width: 1200px;
  margin: 0 auto;
  background-color: #fff;
}

.category-block {
  margin-bottom: 30px;
}

.category-title {
  font-size: 1.2rem;
  margin-bottom: 15px;
  color: #333;
  border-bottom: 1px solid #ddd;
  padding-bottom: 5px;
}

.links-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
  gap: 10px;
}

.link-item {
  display: block;
  padding: 10px 12px;
  background-color: #f5f5f5;
  border-radius: 4px;
  text-decoration: none;
  color: #333;
  text-align: center;
  transition: background-color 0.2s;
  font-size: 0.9rem;
  word-break: keep-all;
  line-height: 1.3;
  overflow-wrap: break-word;
}

.link-item:hover {
  background-color: #e0e0e0;
}

@media (max-width: 768px) {
  .links-grid {
    grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
  }

  .link-item {
    padding: 8px 10px;
    font-size: 0.8rem;
  }
}

@media (max-width: 480px) {
  .links-grid {
    grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
  }

  .link-item {
    padding: 6px 8px;
    font-size: 0.75rem;
  }
}
</style>
