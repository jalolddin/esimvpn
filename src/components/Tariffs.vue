<template>
  <div class="tariff-container">
    <div
      v-for="(tariff, index) in tariffs"
      :key="index"
      class="tariff-card"
      :class="{ selected: selectedTariff === index }"
      @click="selectTariff(index)"
    >
      <div class="tariff-info">
        <div class="tariff-info-card">
          <p>{{ tariff.info1 }}</p>
          <span>{{ tariff.date1 }}</span>
        </div>
        <div class="tariff-info-card">
          <p>{{ tariff.info2 }}</p>
          <span>{{ tariff.date2 }}</span>
        </div>
        <div class="tariff-info-card tariff-info-discount-container">
          <div v-if="tariff.discount" class="tariff-info-discount">
            <span></span>
            <p>{{ tariff.discount }}</p>
            <span></span>
          </div>
        </div>
        <div class="tariff-info-card tariff-info-price">
          <p :style="{ color: tariff.oldPrice ? '#ff86a4' : '#f0f3f7' }">
            $ {{ tariff.price }}
          </p>
          <span v-if="tariff.oldPrice">
            <del>$ {{ tariff.oldPrice }}</del>
          </span>
        </div>
        <div class="tariff-info-price-mobile">
          <div class="tariff-info-card">
            <p :style="{ color: tariff.oldPrice ? '#ff86a4' : '#f0f3f7' }">
              $ {{ tariff.price }}
            </p>
            <span v-if="tariff.oldPrice">
              <del>$ {{ tariff.oldPrice }}</del>
            </span>
          </div>
          <div v-if="tariff.discount" class="tariff-info-discount">
            <span></span>
            <p>{{ tariff.discount }}</p>
            <span></span>
          </div>
        </div>
      </div>
      <div class="checkbox-container">
        <input
          type="radio"
          :checked="selectedTariff === index"
          @click.stop="selectTariff(index)"
        />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const tariffs = ref([
  {
    info1: '500 MB',
    date1: '7 days eSIM',
    info2: '∞ GB',
    date2: '7 days VPN',
    price: '10.00',
  },
  {
    info1: '1 GB',
    date1: '30 days eSIM',
    info2: '∞ GB',
    date2: '30 days VPN',
    price: '20.00',
  },
  {
    info1: '3 GB',
    date1: '30 days eSIM',
    info2: '∞ GB',
    date2: '30 days VPN',
    price: '30.00',
  },
  {
    info1: '5 GB',
    date1: '7 days eSIM',
    info2: '∞ GB',
    date2: '6 months VPN',
    price: '42.12',
    oldPrice: '50.00',
  },
  {
    info1: '10 GB',
    date1: '60 days eSIM',
    info2: '∞ GB',
    date2: '6 months VPN',
    discount: '-50%',
    price: '51.03',
    oldPrice: '60.00',
  },
  {
    info1: '20 GB',
    date1: '60 days eSIM',
    info2: '∞ GB',
    date2: '1 year VPN',
    discount: '-50%',
    price: '80.00',
  },
]);

const selectedTariff = ref(0);
const selectTariff = (index) => {
  selectedTariff.value = index;
};
</script>

<style scoped lang="scss">
.tariff-container {
  display: flex;
  flex-direction: column;
  width: 100%;
  gap: 12px;
  margin-bottom: 24px;
}

.tariff-card {
  width: 100%;
  border: 2px solid #ffffff1f;
  border-radius: 12px;
  padding: 10px 20px;
  cursor: pointer;
  transition:
    transform 0.4s,
    border-color 0.2s;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  box-sizing: border-box;
}
.tariff-card.selected {
  border-color: #775cff;
}

.tariff-info {
  flex: 1;
  display: flex;
  justify-content: space-between;
  align-items: center;
  &-card {
    display: flex;
    flex-direction: column;
    gap: 0.3rem;
    width: 33%;
    p {
      font-size: 20px;
      font-weight: 700;
      color: #f0f3f7;
    }
    span {
      font-size: 14px;
      color: #7f8a9f;
    }
  }
  &-discount {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    padding: 4px 10px;
    gap: 12px;
    height: 22px;
    background: linear-gradient(270deg, #b947ff 0%, #8a73ff 100%);
    font-weight: 700;
    font-size: 12px;
    letter-spacing: 0.02em;
    color: #ffffff;
    position: relative;
    width: max-content;
    &-container {
      display: flex;
      align-items: flex-start;
      width: 150px;
    }
    span:first-child {
      position: absolute;
      width: 10px;
      height: 10px;
      left: -4px;
      top: calc(50% - 4px);
      border-radius: 50%;
      background: #181e29;
    }
    span:last-child {
      position: absolute;
      width: 10px;
      height: 10px;
      right: -4px;
      top: calc(50% - 4px);
      border-radius: 50%;
      background: #181e29;
    }
  }
  &-price {
    align-items: flex-end;
  }
}

.checkbox-container {
  margin-left: 8px;
  input[type='radio'] {
    appearance: none;
    -webkit-appearance: none;
    -moz-appearance: none;
    width: 24px;
    height: 24px;
    border: 1px solid #ffffff3d;
    border-radius: 50%;
    background-color: transparent;
    position: relative;
    cursor: pointer;
  }

  input[type='radio']:checked {
    background-color: #775cff;
    border-color: #775cff;
  }

  input[type='radio']:checked::after {
    content: '';
    position: absolute;
    top: 7px;
    left: 7px;
    width: 8px;
    height: 8px;
    background-color: white;
    border-radius: 50%;
  }
}
.tariff-info-price-mobile {
  display: none;
}
@media (max-width: 550px) {
  .checkbox-container {
    position: absolute;
    top: 15px;
    right: 15px;
  }
  .tariff-info-price,
  .tariff-info-discount-container {
    display: none;
  }
  .tariff-info-price-mobile {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
  }
  .tariff {
    &-card {
      position: relative;
      align-items: flex-start;
    }
    &-info {
      flex-direction: column;
      align-items: flex-start;
      gap: 1rem;
      &-card {
        width: auto;
      }
      &-price {
        align-items: flex-start;
      }
    }
  }
}
</style>
