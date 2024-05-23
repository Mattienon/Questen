<template>
    <div class="card">
      <div class="cardtitle">
        <h1>{{ title }}</h1>
      </div>
      <div class="cardcontent">
        <h2>{{ subtitle }}</h2>
        <span class="text">{{ content }}</span>
        <!-- Video -->
        <div class="videocontainer">
          <iframe :src="videoUrl" frameborder="0" allowfullscreen></iframe>
        </div>
       
      </div> 
      <div class="btn btn-dark">
            <span>KØB BILLET</span>
        </div>
    </div>
  </template>
  
  <script setup>
  import { defineProps } from 'vue';
  const videoUrl = 'https://www.youtube.com/embed/_boQBz9UrHI';
  </script>
  
  <style lang="scss" scoped>
  @import '@/assets/hexcolors.scss';
  
  .card {
    background-color: $secondary-purple;
    border: none;
    width: 100%;
    height: 50vh;
    display: flex;
    align-items: center;
     justify-content: center;
    margin: auto;
  }
.btn{
    padding: 15px;
    background-color: $primary-green;
}
.btn:hover{
    background-color: rgba(3, 95, 3, 0.76);
    transform: 3s ease-in;
}
span{
    font-size: 40px;
}
  .videocontainer iframe {
    width: 710px;
    height: 400px;
    padding: 10%;
  }

  @media (max-width: 600px){
   .videocontainer iframe{
    width: 350px;
    height: 250px;
  }
  .btn{
    padding: 5px 15px;
    background-color: $primary-green;
}
span{
    font-size: 30px;
}
}

  </style>
  