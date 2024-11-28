<template>
  <Navbar />
  <div class="content">
    <router-view/>
  </div>
  <Footer />
</template>

<script setup>
import Navbar from '@/components/Navbar.vue';
import Footer from '@/components/Footer.vue';
</script>

<style lang="scss">
.content{
  max-width: 1184px;
  margin: 0 auto;
  margin-top: 6rem;
  margin-bottom: 6rem;
}
</style>
