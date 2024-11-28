<template>
    <nav class="breadcrumb" aria-label="breadcrumb">
      <ol class="breadcrumb__list">
        <li 
          v-for="(crumb, index) in crumbs" 
          :key="index" 
          class="breadcrumb__item"
          :class="{ 'breadcrumb__item--active': index === crumbs.length - 1 }"
        >
          <!-- Render a span for the last breadcrumb, and a link for others -->
          <span v-if="index === crumbs.length - 1">{{ crumb.name }}</span>
          <a v-else :href="crumb.path">{{ crumb.name }}</a>
          <!-- Add separator unless it's the last breadcrumb -->
          <span v-if="index !== crumbs.length - 1" class="breadcrumb__separator"> / </span>
        </li>
      </ol>
    </nav>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  // Define breadcrumbs as an array of objects
  const crumbs = ref([
    { name: 'Home', path: '/' },
    { name: 'Region', path: '/' },
    { name: 'Europe', path: '/' },
  ]);
  </script>
  
  <style scoped>
  .breadcrumb {
    display: flex;
    align-items: center;
    font-size: 0.9rem;
  }
  
  .breadcrumb__list {
    display: flex;
    gap: 0.5rem;
    list-style: none;
    margin: 0;
    padding: 0;
  }
  
  .breadcrumb__item {
    font-size: 14px;
    color: #F0F3F7;
    display: flex;
    align-items: center;
  }
  
  .breadcrumb__item a {
    text-decoration: none;
    color: inherit;
    transition: color 0.2s;
  }
  
  .breadcrumb__item a:hover {
    color: #775CFF;
  }
  
  .breadcrumb__item--active {
    color: #7F8A9F;
  }
  
  .breadcrumb__separator {
    margin-left: 1.25rem;
    margin-right: 0.5rem;
    color: #7F8A9F;
  }
  </style>