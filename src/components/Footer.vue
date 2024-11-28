<template>
    <footer class="footer">
        <p>© 2024 Esimvpn, All Rights Reserved.</p>
        <a href="#">Terms of Use</a>
        <a href="#">Privacy Policy</a>
    </footer>
  </template>
  
  <script setup>
  import { defineProps } from 'vue';
  
  // Define props for the logo source
  const props = defineProps({
    logoSrc: {
      type: String,
      default: 'https://www.logologo.com/logos/letter-g-leaf-free-logo.jpg',
    },
  });
  </script>
  
  <style scoped lang="scss">
  .footer {
    width: 100%;
    box-sizing: border-box;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    padding: 1.5rem 0;
    gap: 16px;
    position: absolute;
    height: 41px;
    left: 0;
    right: 0;
    bottom: 0;
    border-top: 1px solid #272E3C;
    color: #7F8A9F;
    font-size: 12px;
    background: #010006;
    a{
      color: #7F8A9F;
      text-decoration: underline;
    }
  }
  </style>