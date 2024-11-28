<template>
  <Navbar />
  <div class="effect"></div>
  <div class="content">
    <router-view />
  </div>
  <div class="chatbot">
    <img src="@/assets/icons/chatbot.svg" alt="" />
  </div>
  <Footer />
</template>

<script setup>
import Navbar from '@/components/Navbar.vue';
import Footer from '@/components/Footer.vue';
</script>
