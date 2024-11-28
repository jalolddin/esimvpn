<template>
  <nav class="breadcrumb" aria-label="breadcrumb">
    <ol class="breadcrumb__list">
      <li
        v-for="(crumb, index) in crumbs"
        :key="index"
        class="breadcrumb__item"
        :class="{ 'breadcrumb__item--active': index === crumbs.length - 1 }"
      >
        <span v-if="index === crumbs.length - 1">{{ crumb.name }}</span>
        <a v-else :href="crumb.path">{{ crumb.name }}</a>
        <span v-if="index !== crumbs.length - 1" class="breadcrumb__separator">
          /
        </span>
      </li>
    </ol>
  </nav>
</template>

<script setup>
import { ref } from 'vue';

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
  color: #f0f3f7;
  display: flex;
  align-items: center;
}

.breadcrumb__item a {
  text-decoration: none;
  color: inherit;
  transition: color 0.2s;
}

.breadcrumb__item a:hover {
  color: #775cff;
}

.breadcrumb__item--active {
  color: #7f8a9f;
}

.breadcrumb__separator {
  margin-left: 1.25rem;
  margin-right: 0.5rem;
  color: #7f8a9f;
}
</style>
