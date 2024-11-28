<template>
  <footer class="footer">
    <p>© 2024 Esimvpn, All Rights Reserved.</p>
    <a href="#">Terms of Use</a>
    <a href="#">Privacy Policy</a>
  </footer>
</template>

<script setup></script>

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
  left: 0;
  right: 0;
  bottom: 0;
  border-top: 1px solid #272e3c;
  color: #7f8a9f;
  font-size: 12px;
  background: #010006;
  a {
    color: #7f8a9f;
    text-decoration: underline;
  }
}
@media (max-width: 435px) {
  .footer {
    flex-direction: column-reverse;
  }
}
</style>
