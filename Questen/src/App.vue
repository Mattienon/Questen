<template>
  <div>
    <HeaderLinks />
    <transition name="fade">
      <router-view />
    </transition>
    <ToTheTop />
  </div>
</template>

<script setup>
import { RouterView } from 'vue-router';
import HeaderLinks from './components/Essentials/headerlinks.vue';
import ToTheTop from './components/Essentials/totheTOP.vue';
</script>

<style lang="scss" scoped>
@import '@/assets/hexcolors.scss';

.fade-enter-active,
.fade-leave-active {
  transition: all 0.5s ease-in-out;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
  transform: translateY(50px);
}
</style>
