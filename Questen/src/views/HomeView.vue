<template>
    <div class="home-view body">   

      <div class="heroarea">
          <hero/>
      </div>  
    <div class="outerim">
      <!-- Info Boxes -->
      <div class="info-boxes">
        <infoboxes />
      </div>

      <!-- Logo Area -->
      <div class="logoarea">
        <logoarea />
      </div>
      <!-- Additional Info -->
   
        <additionalinfo />
  

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
  margin-top: 20%;
}

$notchSize: 15px;

.outerim {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: relative;
  width: 88%;
  margin-top: -22%; /* Adjust based on your design */
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

.heroarea {
  width: 95%;
  z-index: 5; /* Ensuring it is above the outerim */
  margin-top: 8%;
  z-index: 10;
}

.bottom-card {
  width: 100%;
  z-index: 2;
  padding-bottom: 8%;
  padding-top: 8%;
}
.logoarea{
  margin-bottom: 10%;
}
// Media queries

@media (max-width: 800px) {
  .info-boxes, .additional-info, .logo-area{
    align-items: center;
    margin: auto;
    width: 85%;
    padding: 2%;
    padding-top: 8%;
  }
  .outerim {
    margin-top: -45%;
    padding-top: 15%;
    width: 95%;
  }

  .logoarea {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 20%;
   
  }
}

@media (max-width: 360px) {
  .logo-area{
    padding: 40%;
  }
  .outerim {
    margin-top: -70%;
    padding-top: 40%;
    width: 95%;
  }
  .info-boxes, .additional-info {
    align-items: center;
    margin: auto;
    width: 85%;
    padding: 0;
  }
}
</style>

