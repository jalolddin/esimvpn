<template>
  <div class="tabs-container">
    <button
      :class="[
        'tab-button',
        { 'tab-button--active': activeTab === 'features' },
      ]"
      @click="setActiveTab('features')"
    >
      Features
    </button>
    <button
      :class="[
        'tab-button',
        { 'tab-button--active': activeTab === 'tech-specs' },
      ]"
      @click="setActiveTab('tech-specs')"
    >
      Tech Specs
    </button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const activeTab = ref('features');

const setActiveTab = (tab) => {
  activeTab.value = tab;
};
</script>

<style scoped lang="scss">
.tabs-container {
  display: flex;
  align-items: center;
  gap: 8px;
  margin: 1.4rem 0;
}

.tab-button {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 9px 16px;
  gap: 5px;
  height: 40px;
  background: #f0f3f7;
  border: 1px solid #ffffff1f;
  border-radius: 100px;
  font-size: 16px;
  font-weight: 400;
  cursor: pointer;
  transition: all 0.3s ease;
}

.tab-button--active {
  background: #f0f3f7;
  color: #272e3c;
}

.tab-button:not(.tab-button--active) {
  background: none;
  border-color: #ffffff1f;
  color: #f0f3f7;
  &:hover {
    background: #ffffff14;
  }
}

.tab-content {
  font-size: 16px;
  text-align: center;
}
</style>
