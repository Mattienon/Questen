<template>
  <div class="body">
    <div class="outerim">
      <gallery />
    </div>
  </div>
  <footnav/>
</template>

<script setup>
import Gallery from '@/components/Gallery/gallery.vue';
import footnav from '@/components/Essentials/footnav.vue'; 
</script>

<style lang="scss" scoped>
@import '@/assets/hexcolors.scss';

.body {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100%;
}
$notchSize: 15px;

.outerim {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: relative; /* Changed from absolute to relative */
  width: 88%;
  margin-top: 2%; /* To adjust top position */
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
</style>
