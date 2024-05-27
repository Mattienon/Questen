<template>
  <div class="video-container">
    <video class="circular-video" autoplay loop muted playsinline>
      <source src="@/assets/Videos/logo.mp4" type="video/mp4">
    </video>
    <a href="https://www.universe.com/events/fantasy-quest-aftenquest-tickets-2PCHR4" class="invisible-button"></a>
  </div>
</template>

<script setup>
</script>

<style lang="scss" scoped>
@import '@/assets/hexcolors.scss';

.video-container {
  position: relative;
  width: 400px;
  height: 400px;
  border-radius: 50%;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  border: none;
  box-shadow: 
    0 0 0 10px $primary-yellow, 
    0 0 0 25px $primary-purple, 
    0 0 0 45px $primary-yellow, 
    0 50px 80px rgba(0, 0, 0, 0.2);
  transition: transform 0.5s ease, box-shadow 0.3s ease;
}

.video-container:hover {
  transform: scale(1.1);
  box-shadow: 
    0 0 0 5px $primary-yellow, 
    0 0 0 15px transparent, 
    0 0 0 20px $primary-green, 
    0 70px 100px rgba(0, 0, 0, 0.3);
}

.circular-video {
  width: 100%;
  height: 100%;
  object-fit: cover;
  pointer-events: none; /* Prevents video controls from interfering with click */
}

.invisible-button {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 10; 
  text-decoration: none;
}

@media (max-width: 700px) {
  .video-container {
    width: 300px;
    height: 300px;
    box-shadow: 
      0 0 0 4px $primary-yellow, 
      0 0 0 10px transparent, 
      0 0 0 14px $primary-purple, 
      0 50px 80px rgba(0, 0, 0, 0.2);
  }

  .video-container:hover {
    box-shadow: 
      0 0 0 4px $primary-yellow,
      0 0 0 10px transparent, 
      0 0 0 14px $primary-purple, 
      0 70px 100px rgba(0, 0, 0, 0.3);
  }
}
</style>

