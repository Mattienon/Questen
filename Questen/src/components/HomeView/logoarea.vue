<template>
  <div class="video-container">
    <video class="circular-video" autoplay loop muted playsinline>
      <source src="@/assets/Videos/logo.mp4" type="video/mp4">
    </video>
  </div>
</template>
<script setup>
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
    0 0 0 10px $primary-yellow, /* First ring */
    0 0 0 25px $primary-purple, /* Space between the rings */
    0 0 0 45px $primary-yellow, /* Second ring */
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

@media (max-width: 700px) {
  .video-container {
    width: 300px; /* Set the width of the circle for smaller screens */
    height: 300px;
    box-shadow: 
      0 0 0 4px $primary-yellow, /* Adjusted first ring for smaller screens */
      0 0 0 10px transparent, /* Space between the rings */
      0 0 0 14px $primary-purple, /* Adjusted second ring for smaller screens */
      0 50px 80px rgba(0, 0, 0, 0.2); /* Adjusted shadow for smaller screens */
  }

  .video-container:hover {
    box-shadow: 
      0 0 0 4px $primary-yellow, /* Adjusted first ring for smaller screens */
      0 0 0 10px transparent, /* Space between the rings */
      0 0 0 14px $primary-purple, /* Adjusted second ring for smaller screens */
      0 70px 100px rgba(0, 0, 0, 0.3); /* Adjusted shadow for smaller screens */
  }
}

</style>
