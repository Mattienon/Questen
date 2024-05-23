<template>
  <div class="home-view">
    <!-- Hero Area -->
    <div class="hero-area">
      <hero />
    </div>

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

    <!-- Placeholder Content -->
  </div>

 
</template>

<script setup>
import additionalinfo from '../components/HomeView/additionalinfo.vue';
import hero from '@/components/HomeView/hero.vue';
import bottomcard from '@/components/HomeView/bottomcard.vue';
import logoarea from '@/components/HomeView/logoarea.vue';
import infoboxes from '@/components/HomeView/infoboxes.vue';
</script>

<style lang="scss" scoped>
.home-view {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  z-index: 10;
  margin-top: 10%;
}
.hero-area{
width: 95%;
z-index: 20;
}
.additional-info{
  margin-top: 8%;;
}
.bottom-card{
  margin-top: 10%;
  width: 95%;
  z-index: 20;
}


//media


@media (max-width: 1024px) {
    .info-boxes, .additional-info, .logo-area{
      align-items: center;
      margin: auto;
      width: 85%;
      padding: 5%
      
      
    }
    .logo-area{
      margin-left: 14%;
    }
    }

    @media (max-width: 600px) {
      .logo-area{
      display: none;
    }
    .info-boxes, .additional-info, .logo-area{
      align-items: center;
      margin: auto;
      width: 85%;
      padding: 5%
      
    }
    }

</style>
