<template>
  <div class="root-container">
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

.root-container {
  position: relative;
}

.root-container::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 80%;
  background: radial-gradient(circle at center, $primary-purple 0.1%, white 70%, );
  z-index: -1;
}

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
