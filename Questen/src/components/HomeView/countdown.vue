<template>
    <div class="countdown-container">
      <h1 class="countdown-title"></h1>
      <div class="countdown-time">
        <p v-if="days" class="countdown-segment">{{ days }}D</p>
        <p class="countdown-segment">{{ hours }}T</p>
        <p class="countdown-segment">{{ minutes }}M</p>
        <p class="countdown-segment">{{ seconds }}S</p>
      </div>
    </div>
  </template>
  
  <script>
  import { ref, computed, onMounted } from 'vue';
  
  export default {
    setup() {
      const targetDate = new Date('2024-09-14T20:30:00');
      const currentDate = new Date();
  
      if (targetDate <= currentDate) {
        console.error('Target date must be in the future.');
        return;
      }
  
      let timeLeft = ref(Math.floor((targetDate - currentDate) / 1000));
  
      const days = computed(() => Math.floor(timeLeft.value / 86400));
      const hours = computed(() => Math.floor((timeLeft.value % 86400) / 3600));
      const minutes = computed(() => Math.floor((timeLeft.value % 3600) / 60));
      const seconds = computed(() => timeLeft.value % 60);
  
      const startTimer = () => {
        const timerInterval = setInterval(() => {
          timeLeft.value--;
          if (timeLeft.value <= 0) {
            clearInterval(timerInterval);
            console.log('Timer ended!');
          }
        }, 1000);
      };
  
      onMounted(startTimer);
  
      return {
        days,
        hours,
        minutes,
        seconds
      };
    }
  };
  </script>
  
  <style lang="scss" scoped>
  @import '@/assets/hexcolors.scss';
  
  .countdown-container {
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 100%;
    margin: auto;
  }
  
  .countdown-time {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: auto;
    padding: 30px 50px;
  }
  
  .countdown-segment {
    margin: 5px;
    padding: 40px 20px; 
    font-size: 60px;
    color: $primary-green;
    background-color: $light-purple; 
    border: solid 5px $primary-yellow; 
    border-radius: 10px; 
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2); 
    transition: transform 0.3s ease, color 0.3s ease, background-color 0.3s ease, box-shadow 0.3s ease; 
  }
  
  .countdown-segment:hover {
  transform: scale(1.1) !important;
  color: $primary-yellow !important;
  background-color: lighten($light-purple, 10%) !important;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.3) !important;
}

  
  @media (max-width: 560px) {
    .countdown-container {
      padding: 0;
      margin: 0;
    }
    .countdown-segment {
      font-size: 18px;
      padding: 10px 8px; 
    }
  }
  </style>