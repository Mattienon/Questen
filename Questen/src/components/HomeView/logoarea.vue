<template>
  <div class="video-container" @mouseover="createStars">
    <video class="circular-video" autoplay loop muted playsinline>
      <source src="@/assets/Videos/logo.mp4" type="video/mp4">
    </video>
  </div>
</template>

<script setup>
import anime from 'animejs';

// Function to create a single star particle
const createStar = () => {
  const star = document.createElement('div');
  star.classList.add('star');
  star.style.position = 'absolute';
  star.style.width = '20px';
  star.style.height = '20px';
  star.style.background = '#ffffff'; // Set the color of the star
  star.style.borderRadius = '50%';
  star.style.pointerEvents = 'none';
  star.style.zIndex = '1000'; // Ensure stars appear above other content
  document.querySelector('.video-container').appendChild(star);
  
  // Set initial position and opacity
  anime.set(star, {
    left: Math.random() * window.innerWidth + 'px',
    top: '-10px',
    opacity: 0,
  });
  
  // Animate the star falling and fading in
  anime({
    targets: star,
    top: window.innerHeight + 'px',
    opacity: 1,
    duration: 2000,
    easing: 'radial',
    complete: () => {
      // Remove the star element from the DOM once animation is complete
      star.remove();
    },
  });
};

// Function to create multiple stars
const createStars = () => {
  // Change the number of stars based on the desired density
  for (let i = 0; i < 50; i++) {
    createStar();
  }
};
</script>

<style lang="scss" scoped>
  @import '@/assets/hexcolors.scss';
.video-container {
  width: 400px; /* Set the width of the circle */
  height: 400px; /* Set the height of the circle */
  border-radius: 50%; /* Make the container circular */
  overflow: hidden; /* Ensure the video fits within the circle */
  display: flex;
  align-items: center;
  justify-content: center;
  border: none; /* Remove the default border */
  box-shadow: 
    0 0 0 5px $primary-yellow, /* First ring */
    0 0 0 15px $primary-purple, /* Space between the rings */
    0 0 0 35px $primary-yellow, /* Second ring */
    0 50px 80px rgba(0, 0, 0, 0.2); /* Add shadow to card */
  transition: transform 0.5s ease, box-shadow 0.3s ease; /* Smooth transition for shadow and transform */
}

.video-container:hover {
  transform: scale(1.1); /* Slightly increase size on hover */
  box-shadow: 
    0 0 0 5px $primary-yellow, /* First ring */
    0 0 0 15px transparent, /* Space between the rings */
    0 0 0 20px $primary-green, /* Second ring */
    0 70px 100px rgba(0, 0, 0, 0.3); /* Enhance shadow on hover */
}

.circular-video {
  width: 100%;
  height: 100%;
  object-fit: cover; /* Ensure the video covers the entire circular container */
  pointer-events: none; /* Disable user interaction with the video element */
}
</style>
