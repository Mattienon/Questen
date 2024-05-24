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
  const videoUrl = 'https://www.youtube.com/embed/_boQBz9UrHI';
  </script>
  
  <style lang="scss" scoped>
  @import '@/assets/hexcolors.scss';
  
  .card {
    background: linear-gradient(to bottom, transparent, $secondary-purple 20% 90%, transparent);
    border: none;
    width: 100%;
    height: 50vh;
    display: flex;
    align-items: center;
     justify-content: center;
      margin-bottom: 8%;
  }
.btn{
  z-index: 2;
  margin-top: -8%;
    padding: 12px;
    background-color: $primary-green;
    border: none;
    box-shadow: 0 0px 2px rgba(0, 0, 0, 0.3); 
}
  .btn:hover{
    transform: ease-in 0.6s scale(1.5); 
    color: $primary-yellow; 
    background-color: lighten($light-purple, 10%); 
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.3); 
  }
span{
    font-size: 33px;
}
  .videocontainer iframe {
    width: 1080px;
    height: 700px;
    padding: 10%;
    border-radius: 50%;

  }

  @media (max-width: 1000px){
   .videocontainer iframe{
    width: 650px;
    height: 400px; 
  }
  .btn{
    padding: 5px 15px;
    background-color: $primary-green;
}
span{
    font-size: 30px;
}
}

@media (max-width: 400px){
   .videocontainer iframe{
    width: 350px;
    height: 300px; 
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
  