<template>
  <nav class="navbar">
    <div class="navbar__container">
      <router-link to="/"
        ><img src="@/assets/icons/logo.svg" alt=""
      /></router-link>
      <div class="navbar__links">
        <router-link to="/" class="navbar__help"
          ><img src="@/assets/icons/help.svg" alt="" /> Help</router-link
        >
        <button class="primary-button">Get started</button>
      </div>
    </div>
  </nav>
</template>

<script setup></script>

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
    a {
      display: flex;
      gap: 4px;
      font-size: 16px;
      color: #f0f3f7;
    }
    button {
      height: 40px;
      padding: 8px 18px;
    }
  }
  @media (max-width: 1195px) {
    .navbar {
      &__container {
        padding: 2.2rem 1.2rem;
      }
    }
  }

  @media (max-width: 500px) {
    .navbar__links {
      a {
        display: none;
      }
      button {
        font-size: 12px;
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
      svg {
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
