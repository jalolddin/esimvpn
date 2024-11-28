<template>
  <nav class="navbar">
    <div class="navbar__container">
      <router-link to="/"><img src="@/assets/icons/logo.svg" alt=""></router-link>
      <div class="mobile-menu" @click="toggleSidebar">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512">
          <path
            d="M0 96C0 78.3 14.3 64 32 64l384 0c17.7 0 32 14.3 32 32s-14.3 32-32 32L32 128C14.3 128 0 113.7 0 96zM0 256c0-17.7 14.3-32 32-32l384 0c17.7 0 32 14.3 32 32s-14.3 32-32 32L32 288c-17.7 0-32-14.3-32-32zM448 416c0 17.7-14.3 32-32 32L32 448c-17.7 0-32-14.3-32-32s14.3-32 32-32l384 0c17.7 0 32 14.3 32 32z"
          />
        </svg>
      </div>
      <div class="navbar__links">
        <router-link to="/" class="navbar__help"><img src="@/assets/icons/help.svg" alt=""> Help</router-link>
        <button class="primary-button">Get started</button>
      </div>
    </div>

    <!-- Sidebar -->
    <!-- <div class="sidebar" :class="{ 'sidebar--open': isSidebarOpen }">
      <div class="sidebar__header">
        <h2>Hadyador</h2>
        <svg @click="toggleSidebar" class="sidebar-close-btn" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 384 512"><path d="M342.6 150.6c12.5-12.5 12.5-32.8 0-45.3s-32.8-12.5-45.3 0L192 210.7 86.6 105.4c-12.5-12.5-32.8-12.5-45.3 0s-12.5 32.8 0 45.3L146.7 256 41.4 361.4c-12.5 12.5-12.5 32.8 0 45.3s32.8 12.5 45.3 0L192 301.3 297.4 406.6c12.5 12.5 32.8 12.5 45.3 0s12.5-32.8 0-45.3L237.3 256 342.6 150.6z"/></svg>
      </div>

      <div class="sidebar__content">
        <router-link to="/products" class="sidebar__link" @click="toggleSidebar">Mahsulotlar</router-link>
        <router-link to="/contact" class="sidebar__link" @click="toggleSidebar">Bog'lanish</router-link>
      </div>


      <div class="sidebar__footer">
        <a href="https://www.instagram.com/ijaxongirmirzo" target="_blank" class="social-link">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M224.1 141c-63.6 0-114.9 51.3-114.9 114.9s51.3 114.9 114.9 114.9S339 319.5 339 255.9 287.7 141 224.1 141zm0 189.6c-41.1 0-74.7-33.5-74.7-74.7s33.5-74.7 74.7-74.7 74.7 33.5 74.7 74.7-33.6 74.7-74.7 74.7zm146.4-194.3c0 14.9-12 26.8-26.8 26.8-14.9 0-26.8-12-26.8-26.8s12-26.8 26.8-26.8 26.8 12 26.8 26.8zm76.1 27.2c-1.7-35.9-9.9-67.7-36.2-93.9-26.2-26.2-58-34.4-93.9-36.2-37-2.1-147.9-2.1-184.9 0-35.8 1.7-67.6 9.9-93.9 36.1s-34.4 58-36.2 93.9c-2.1 37-2.1 147.9 0 184.9 1.7 35.9 9.9 67.7 36.2 93.9s58 34.4 93.9 36.2c37 2.1 147.9 2.1 184.9 0 35.9-1.7 67.7-9.9 93.9-36.2 26.2-26.2 34.4-58 36.2-93.9 2.1-37 2.1-147.8 0-184.8zM398.8 388c-7.8 19.6-22.9 34.7-42.6 42.6-29.5 11.7-99.5 9-132.1 9s-102.7 2.6-132.1-9c-19.6-7.8-34.7-22.9-42.6-42.6-11.7-29.5-9-99.5-9-132.1s-2.6-102.7 9-132.1c7.8-19.6 22.9-34.7 42.6-42.6 29.5-11.7 99.5-9 132.1-9s102.7-2.6 132.1 9c19.6 7.8 34.7 22.9 42.6 42.6 11.7 29.5 9 99.5 9 132.1s2.7 102.7-9 132.1z"/></svg>
        </a>
        <a href="https://www.youtube.com/@ijahongirmirzo" target="_blank" class="social-link">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512"><path d="M549.7 124.1c-6.3-23.7-24.8-42.3-48.3-48.6C458.8 64 288 64 288 64S117.2 64 74.6 75.5c-23.5 6.3-42 24.9-48.3 48.6-11.4 42.9-11.4 132.3-11.4 132.3s0 89.4 11.4 132.3c6.3 23.7 24.8 41.5 48.3 47.8C117.2 448 288 448 288 448s170.8 0 213.4-11.5c23.5-6.3 42-24.2 48.3-47.8 11.4-42.9 11.4-132.3 11.4-132.3s0-89.4-11.4-132.3zm-317.5 213.5V175.2l142.7 81.2-142.7 81.2z"/></svg>
        </a>
        <a href="https://telegram.me/ijahongirmirzo" target="_blank" class="social-link">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 496 512"><path d="M248 8C111 8 0 119 0 256S111 504 248 504 496 393 496 256 385 8 248 8zM363 176.7c-3.7 39.2-19.9 134.4-28.1 178.3-3.5 18.6-10.3 24.8-16.9 25.4-14.4 1.3-25.3-9.5-39.3-18.7-21.8-14.3-34.2-23.2-55.3-37.2-24.5-16.1-8.6-25 5.3-39.5 3.7-3.8 67.1-61.5 68.3-66.7 .2-.7 .3-3.1-1.2-4.4s-3.6-.8-5.1-.5q-3.3 .7-104.6 69.1-14.8 10.2-26.9 9.9c-8.9-.2-25.9-5-38.6-9.1-15.5-5-27.9-7.7-26.8-16.3q.8-6.7 18.5-13.7 108.4-47.2 144.6-62.3c68.9-28.6 83.2-33.6 92.5-33.8 2.1 0 6.6 .5 9.6 2.9a10.5 10.5 0 0 1 3.5 6.7A43.8 43.8 0 0 1 363 176.7z"/></svg>
        </a>
      </div>
    </div> -->
  </nav>
</template>

<script setup>
import { ref } from 'vue';

// State to track sidebar visibility
const isSidebarOpen = ref(false);

// Function to toggle sidebar
const toggleSidebar = () => {
  isSidebarOpen.value = !isSidebarOpen.value;
};
</script>

<style scoped lang="scss">
.navbar {
box-sizing: border-box;
display: flex;
flex-direction: column;
justify-content: center;
align-items: center;
position: absolute;
height: 72px;
left: 0;
top: 0;
width: 100%;
background: black;
border-bottom: 1px solid rgba(255, 255, 255, 0.08);

  &__container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    max-width: 1184px;
    width: 100%;
    margin: 0 auto;
    padding: 2.2rem 0;
    box-sizing: border-box;
  }

  &__logo {
    cursor: pointer;
    font-size: 1.9rem;
    letter-spacing: 2px;
  }

  &__links {
    display: flex;
    align-items: center;
    gap: 1.5rem;
    a{
      display: flex;
      gap: 4px;
      font-size: 16px;
      color: #F0F3F7;
    }
    button{
      height: 40px;
      padding: 8px 18px;
      
    }
  }

  @media (max-width: 768px) {
    .navbar__links {
      display: none;
    }

    .mobile-menu {
      display: flex;
      svg {
        height: 2rem;
        width: 2rem;
        fill: white;
        cursor: pointer;
      }
    }
  }
}

/* Sidebar Styles */
.sidebar {
  position: fixed;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background-color: #333;
  color: white;
  transition: left 0.3s ease;
  z-index: 1000;
  display: flex;
  flex-direction: column;
  justify-content: space-between;

  &--open {
    left: 0;
  }

  &__header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1.5rem;
    background-color: #444;
    color: #fff;

    h2 {
      margin: 0;
    }

    .sidebar-close-btn {
      fill: white;
      height: 2rem;
      width: 2rem;
      cursor: pointer;
    }
  }

  &__content {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
    padding: 2rem;

    .sidebar__link {
      color: #fff;
      text-decoration: none;
      font-size: 1.2rem;
      font-weight: bold;

      &:hover {
        color: #3498db;
      }
    }
  }

  &__footer {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 1.5rem;
    padding: 1.5rem;
    background-color: #444;

    .social-link {
      color: #fff;
      text-decoration: none;
      font-size: 1rem;
      svg{
        height: 2.5rem;
        width: 2.5rem;
        fill: white;
      }
      &:hover {
        color: #3498db;
      }
    }
  }
}
</style>