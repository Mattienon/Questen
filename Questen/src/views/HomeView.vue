<template>
    <div class="home-view body">   

      <div class="hero-area">
          <hero/>
      </div>  
    <div class="outerim">
      <!-- Info Boxes -->
      <div class="info-boxes">
        <infoboxes />
      </div>

      <!-- Logo Area -->
      <div class="logo-area">
        <logoarea />
      </div>

      <!-- Additional Info -->
      <div class="additional-info">
        <additionalinfo />
      </div>

      <!-- Bottom Card -->
      <div class="bottom-card">
        <bottomcard />
      </div>
    </div>
    <footnav/>
  </div>
</template>

<script setup>
import additionalinfo from '../components/HomeView/additionalinfo.vue';
import hero from '@/components/HomeView/hero.vue';
import bottomcard from '@/components/HomeView/bottomcard.vue';
import logoarea from '@/components/HomeView/logoarea.vue';
import infoboxes from '@/components/HomeView/infoboxes.vue';
import footnav from '@/components/Essentials/footnav.vue'; 
</script>

<style lang="scss" scoped>
@import '@/assets/hexcolors.scss';

.home-view {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  z-index: 10;
}

.info-boxes{
  margin-top: 25%;
}
$notchSize: 15px;

.outerim {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: relative;
  width: 88%;
  margin-top: -23%; /* Adjust based on your design */
  z-index: 1; /* Ensuring it is below the hero area */
  border: 10px outset $primary-yellow;
  background: linear-gradient(to bottom, $primary-purple 70%, $primary-green 95%);
  clip-path: polygon(
    0% $notchSize, 
    $notchSize 0%, 
    calc(100% - #{$notchSize}) 0%, 
    100% $notchSize, 
    100% calc(100% - #{$notchSize}), 
    calc(100% - #{$notchSize}) 100%, 
    $notchSize 100%, 
    0% calc(100% - #{$notchSize})
  );
}

.hero-area {
  width: 95%;
  z-index: 5; /* Ensuring it is above the outerim */
  margin-top: 8%;
}

.additional-info {
  margin-top: 8%;
}

.bottom-card {
  margin-top: 10%;
  width: 98%;
  z-index: 2;
  padding-bottom: 5%;
}

// Media queries

@media (max-width: 1600px) {
  .info-boxes, .additional-info, .logo-area{
    align-items: center;
    margin: auto;
    width: 85%;
    padding: 5%;
    padding-top: 20%;
  }
  .outerim {
    margin-top: -25%;
    padding-top: 8%;
    width: 95%;
  }

  .logo-area {
    display: flex;
    justify-content: center;
    align-items: center;
   
  }
}

@media (max-width: 360px) {
  .logo-area {
    display: none;
  }
  .outerim {
    margin-top: -80%;
    padding-top: 40%;
    width: 95%;
  }
  .info-boxes, .additional-info, .logo-area {
    align-items: center;
    margin: auto;
    width: 85%;
    padding: 5%;
  }
}
</style>

