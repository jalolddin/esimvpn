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
            <div>
                <p>{{tariff.info1}}</p>
                <span>{{tariff.date1}}</span>
            </div>
            <div>
                <p>{{tariff.info2}}</p>
                <span>{{tariff.date2}}</span>
            </div>
            <div>
                <p>$ {{ tariff.price }}</p>
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
  
  // Tariff data
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
  },
  {
    info1: '10 GB',
    date1: '60 days eSIM',
    info2: '∞ GB',
    date2: '6 months VPN',
    price: '51.03',
  },
  {
    info1: '20 GB',
    date1: '60 days eSIM',
    info2: '∞ GB',
    date2: '1 year VPN',
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
    border: 2px solid #FFFFFF1F;
    border-radius: 12px;
    padding: 10px 20px;
    cursor: pointer;
    transition: transform 0.4s, border-color 0.2s;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    box-sizing: border-box;
  }
  .tariff-card.selected {
    border-color: #775CFF;
  }
  
  .tariff-info {
    flex: 1;
    display: flex;
    justify-content: space-between;
    align-items: center;
    div {
        display: flex;
        flex-direction: column;
        gap: 0.3rem;
        p{
            font-size: 20px;
            font-weight: 700;
            color: #F0F3F7;
        }
        span{
            font-size: 14px;
            color: #7F8A9F;
        }
    }
}
  
  .checkbox-container {
    margin-left: 8px;
    input[type="radio"] {
        appearance: none; 
        -webkit-appearance: none; 
        -moz-appearance: none; 
        width: 24px;
        height: 24px;
        border: 1px solid #FFFFFF3D;
        border-radius: 50%; 
        background-color: transparent;
        position: relative;
        cursor: pointer;
      }
      
      input[type="radio"]:checked {
        background-color: #775CFF;
        border-color: #775CFF;
      }
      
      input[type="radio"]:checked::after {
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

  </style>