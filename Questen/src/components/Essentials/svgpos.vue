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
      translateX: [-2000, window.innerWidth], // Start the video outside the left edge and bring it to the right edge of the window
      duration: 7000, // Adjust the duration of the animation as needed
      easing: 'linear', // Use linear easing for a consistent speed
      loop: true // Loop the animation
    });
  };
  
  import { onMounted } from 'vue';
  
  onMounted(() => {
    animateVideo();
  });
  </script>
  
  <style lang="scss" scoped>
  .video-container {
    position: fixed;
    top: 5%;
    left: 0;
    width: 90%;
    height: 90%;
    z-index: 0;
  }
  
  .video {
    width: 16%;
  }
  </style>