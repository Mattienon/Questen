<template>
    <div class="gallery-container">
      <h1 class="animated-heading">Galleri</h1>
      <div class="row">
        <div v-for="(item, index) in cards" :key="index" class="col-6">
          <div class="card">
            <div class="feather-border">
              <img :src="item.imageUrl" :alt="item.alt">
            </div>
            <br>
            <p>{{ item.text }}</p>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';

  const cards = ref([
    { imageUrl: '', alt: 'Violin image', text: 'Hyggelig musik bliver spillet og hygget om.' },
 
  ]);
  </script>
  
  <style lang="scss" scoped>
  @import '@/assets/hexcolors.scss';
  .gallery-container{
    height: 260vh;
  }


  .row, h1 {
    display: flex;
    justify-content: center;
    margin: auto;
  }
  
  h1 {
    padding-top: 2rem;
    padding-bottom: 1.5rem;
    color: $primary-yellow;
  }
  
  .card {
    width: 95%;
    height: 95%;
    border: solid 8px $primary-yellow;
    padding: 2%;
    text-align: center;
    display: flex;
    margin: auto;
    background-color: transparent;
  }
  
  .feather-border::before,
  .feather-border::after {
    content: '';
    position: absolute;
    top: -1px;
    bottom: -0px;
    left: -0px;
    right: -0px;
    border-radius: 0%;
    background: radial-gradient(circle at center, transparent 50%, black 200%);
  }
  
  img {
    width: 100%;
    height: 200px; /* Set a fixed height for the images */
    object-fit: contain;
    display: block;
  }
  
  .animated-heading {
    margin-top: -5%;
    animation: moveUp ease-in-out 0.5s;
  }
  
  @media (max-width: 700px) {
    .row .col-6 {
      flex-direction: column;
      width: 100%;
      justify-content: center;
      align-items: center;
      padding: 0%;
      margin: 0%;
    }
  }
  
  @keyframes moveUp {
    0% {
      transform: translateY(0);
    }
    10% {
      transform: translateY(-5px);
    }
  }
  </style>