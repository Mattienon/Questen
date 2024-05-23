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
  import violin from '@/assets/images/Violin.jpg'
  import pege from '@/assets/images/pege.jpg'
  import musik from '@/assets/images/musik.jpg'
  import heks from '@/assets/images/heks.jpg'
  import fotograf from '@/assets/images/fotograf.jpg'
  import elf from '@/assets/images/elf.jpg'


  const cards = ref([
  { imageUrl: violin, alt: 'Violin image', text: 'Hyggelig musik bliver spillet og hygget om.' },

  { imageUrl: pege, alt: 'Violin image', text: 'En masse at se.' },

  { imageUrl: musik, alt: 'Violin image', text: 'Flot scene med en masse musik.' },

  { imageUrl: heks, alt: 'Violin image', text: 'Kom og mød Maulice.' },

  { imageUrl: fotograf, alt: 'Violin image', text: 'Hygge områder, hvor du kan spise og drikke.' },

  { imageUrl: elf , alt: 'Violin image', text: 'Mange dygtige skuespillere.' },
 
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
    width: 65%;
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