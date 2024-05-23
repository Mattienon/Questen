<template>
  <div>
    <headerlinks/>
    <main>
        <div class="outerim">  </div> 
          <transition>
              <router-view/>
      </transition>
 
   <!-- outerim -->
  </main>
  <totheTOP />
    <footnav />
  </div>
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
  top: 12%;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 85%;
  min-height: 350vh;
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

@media (max-width: 500px) {
  .outerim {
    min-height: 450vh;
    width: 95%;
  }
}
</style>
