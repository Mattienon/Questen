<template>
  <div class="video-container">
    <video id="myVideo" class="video" autoplay loop>
      <source src="@/assets/Videos/drage.mp4" type="video/mp4">
    </video>
  </div>
</template>

<script setup>
import anime from 'animejs';

const animateVideo = () => {
  anime({
    targets: '#myVideo',
    translateX: [-2000, window.innerWidth], 
    duration: 7000, 
    easing: 'linear',
    loop: true 
  });
};

import { onMounted } from 'vue';

onMounted(() => {
  animateVideo();
});
</script>

<style lang="scss" scoped>
.video-container {
  position: absolute;
  top: 1%;
  left: 0;
  width: 90%;
  height: 90%;
  z-index: 0;
}

.video {
  width: 16%;
  pointer-events: none; 
}

@media (max-width: 1200px) {
  .video-container {
   top: 5%;
  }
  .video {
  width: 25%
}
}

@media (max-width: 800px) {
  .video-container {
    display: none;
  }
}
</style>
