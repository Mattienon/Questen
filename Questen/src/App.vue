<template>
  <div>
    <headerlinks />
    <main>
      <div class="outerim"></div>
      <Transition name="slide-fade">
        <router-view />
      </transition>
    </main>
    <totheTOP />
  </div>
  <footnav />
</template>


<script setup>
import { RouterView } from 'vue-router';
import footnav from '@/components/Essentials/footnav.vue';
import headerlinks from './components/Essentials/headerlinks.vue';
import totheTOP from './components/Essentials/totheTOP.vue';
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

@media (min-width: 1024px) {
  .outerim {
    min-height: 300vh;
    width: 95%;
  }
}

@media (max-width: 1500px) {
  .outerim {
    min-height: 250vh;
    width: 95%;
  }
}

@media (max-width: 800px) {
  .outerim {
    min-height: 350vh;
    width: 95%;
  }
}

@media (max-width: 600px) {
  .outerim {
    min-height: 250vh;
    width: 95%;
  }
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
