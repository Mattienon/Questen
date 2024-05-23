<template>
  <div>
    <HeaderLinks />
    <main>
      <router-view />
    </main>
    <ToTheTop />
  </div>
</template>

<script setup>
import { RouterView } from 'vue-router';
import FootNav from '@/components/Essentials/footnav.vue';
import HeaderLinks from './components/Essentials/headerlinks.vue';
import ToTheTop from './components/Essentials/totheTOP.vue';
</script>

<style lang="scss" scoped>
@import '@/assets/hexcolors.scss';

$notchSize: 15px;

.outerim {
  display: flex;
  justify-content: center;
  align-items: center;
  position: absolute;
  overflow: hidden;
  top: 15%;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 85%;
  z-index: -1;
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

// Consolidated media queries

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
