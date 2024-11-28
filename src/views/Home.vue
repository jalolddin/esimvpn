<template>
  <Breadcrumb />
  <div class="main-container">
    <div class="main-container-image">
      <img src="@/assets/images/banner-image.jpg" alt="" />
    </div>
    <div class="main-container-info">
      <div class="main-container-info-title">
        <img src="@/assets/icons/world.svg" alt="" /> eSIM Europe + VPN
      </div>
      <Tabs />
      <ul class="main-container-info-list">
        <li v-for="(item, index) in items" :key="index">
          {{ item }}
        </li>
      </ul>
      <Tariffs />
      <button @click="toggleModal" class="primary-button">Buy now</button>
      <p class="main-container-info-secure">
        <img src="@/assets/icons/secure.svg" alt="" /> Secure payment
        guaranteed.
      </p>
    </div>
  </div>
  <Modal v-model="isModalVisible">
    <form
      v-if="!isChecked"
      class="modal-content-form"
      action="#"
      @submit.prevent="submitForm"
    >
      <p class="modal-content-form-desc">
        Get in touch with our support team if you need help.
      </p>
      <input
        required
        v-model="formData.email"
        id="email"
        type="email"
        placeholder="Email"
      />
      <textarea
        required
        name="message"
        id="message"
        placeholder="Your message"
      ></textarea>
      <button type="submit" class="primary-button">Send</button>
      <span class="modal-content-form-privacy"
        >By clicking 'Send' I agree with <a href="/"> Privacy Policy </a></span
      >
    </form>
    <div v-else class="modal-success">
      <img src="@/assets/icons/checked.svg" alt="" />
      <p>Your message has been sent</p>
      <button @click="toggleModal">Close</button>
    </div>
  </Modal>
</template>

<script setup>
import { ref } from 'vue';
import Breadcrumb from '@/components/Breadcrumb.vue';
import Tariffs from '@/components/Tariffs.vue';
import Tabs from '@/components/Tabs.vue';
import Modal from '@/components/Modal.vue';

const items = ref([
  '33 countries',
  'Reliable connection from best networks.',
  'You will only get mobile data and keep your original phone number.',
  'Works with all smartphones with eSIM technology.',
]);

const formData = ref({
  name: '',
  phone: '',
  username: '',
});
const isChecked = ref(false);
const submitForm = async () => {
  isChecked.value = true;
};

const isModalVisible = ref(false);
const toggleModal = () => {
  isModalVisible.value = !isModalVisible.value;
};
</script>

<style lang="scss">
.main-container {
  display: flex;
  align-items: flex-start;
  flex-wrap: wrap;
  gap: 96px;
  margin-top: 2rem;
  &-image {
    img {
      height: 585px;
    }
  }
  &-info {
    flex: 1;
    &-title {
      display: flex;
      align-items: center;
      gap: 1rem;
      font-size: 36px;
      font-weight: 700;
    }
    &-list {
      color: #7f8a9f;
      display: flex;
      flex-direction: column;
      gap: 8px;
      font-size: 14px;
      font-weight: 400;
      padding: 0 1.4rem 1.4rem;
    }
    &-secure {
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0.2rem;
      color: #6f7388;
      font-weight: 400;
      font-size: 14px;
      margin-top: 24px;
    }
  }
}
@media (max-width: 1025px) {
  .main-container {
    gap: 45px;
    &-image {
      width: 35%;
      img {
        height: auto;
        width: 100%;
      }
    }
  }
}
@media (max-width: 890px) {
  .main-container {
    &-info {
      width: 100%;
    }
    &-image {
      display: none;
    }
  }
}
@media (max-width: 450px) {
  .main-container {
    &-info {
      &-title {
        font-size: 24px;
      }
    }
  }
}
</style>
