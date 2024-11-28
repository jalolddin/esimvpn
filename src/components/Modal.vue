<template>
  <div v-if="modelValue" class="modal-overlay" @click.self="closeModal">
    <div class="modal-content">
      <div class="modal-content-title">
        <h1>Contact support</h1>
        <svg
          @click="closeModal"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 384 512"
        >
          <path
            d="M342.6 150.6c12.5-12.5 12.5-32.8 0-45.3s-32.8-12.5-45.3 0L192 210.7 86.6 105.4c-12.5-12.5-32.8-12.5-45.3 0s-12.5 32.8 0 45.3L146.7 256 41.4 361.4c-12.5 12.5-12.5 32.8 0 45.3s32.8 12.5 45.3 0L192 301.3 297.4 406.6c12.5 12.5 32.8 12.5 45.3 0s12.5-32.8 0-45.3L237.3 256 342.6 150.6z"
          />
        </svg>
      </div>
      <slot></slot>
    </div>
  </div>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue';

// Props
const props = defineProps({
  modelValue: {
    type: Boolean,
    required: true,
  },
});

// Emits
const emit = defineEmits(['update:modelValue']);

// Methods
const closeModal = () => {
  emit('update:modelValue', false);
};
</script>

<style lang="scss">
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: #010005;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}
.modal-content {
  background: #151324;
  border-radius: 24px;
  max-width: 500px;
  position: relative;
  width: 100%;
  padding: 1.5rem 2rem;
  box-sizing: border-box;
  border: 1px solid rgba(255, 255, 255, 0.08);
  filter: drop-shadow(0px 4px 48px rgba(1, 0, 6, 0.5));
  &-title {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    h1 {
      color: #f0f3f7;
      font-size: 36px;
      font-weight: 700;
    }
    svg {
      width: 24px;
      height: 24px;
      fill: #7f8a9f;
      cursor: pointer;
      margin-top: -0.1rem;
    }
  }
  &-form {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    margin-top: 3rem;
    &-desc {
      color: #7f8a9f;
      font-size: 16px;
      font-weight: 400;
      margin-left: 0.1rem;
    }
    input {
      font-size: 16px;
      font-weight: 400;
      box-sizing: border-box;
      display: flex;
      flex-direction: row;
      align-items: center;
      padding: 17px 16px;
      gap: 12px;
      height: 56px;
      width: 100%;
      background: #272e3c;
      border: 1px solid #272e3c;
      border-radius: 12px;
      color: #fff;
      outline: none;
    }
    textarea {
      font-size: 16px;
      box-sizing: border-box;
      display: flex;
      font-weight: 400;
      flex-direction: row;
      align-items: center;
      padding: 17px 16px;
      gap: 12px;
      height: 144px;
      width: 100%;
      background: #272e3c;
      border: 1px solid #272e3c;
      border-radius: 12px;
      color: #fff;
      outline: none;
    }
    &-privacy {
      display: flex;
      justify-content: center;
      color: #7f8a9f;
      font-size: 12px;
      font-weight: 400;
      a {
        text-decoration: underline;
        color: #7f8a9f;
      }
    }
  }
}
.modal-success {
  margin-top: 3rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 1rem;
  p {
    color: #7f8a9f;
    font-size: 16px;
    font-weight: 400;
  }
  button {
    font-size: 16px;
    font-weight: 500;
    color: #f0f3f7;
    box-sizing: border-box;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 12px 32px 11px;
    gap: 8px;
    width: 100%;
    height: 45px;
    border: 1.25px solid rgba(255, 255, 255, 0.12);
    border-radius: 50px;
    background: none;
    cursor: pointer;
    &:hover {
      background: #ffffff14;
    }
  }
}
@media (max-width: 768px) {
  .modal-content {
    padding: 1.8rem;
    width: 90%;
    max-width: 350px !important;
    &-title {
      h1 {
        font-size: 24px;
      }
    }
    p {
      font-size: 12px;
    }
  }
}
</style>
