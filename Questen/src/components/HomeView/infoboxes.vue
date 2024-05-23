<template>
  <div class="container">
    <div class="row">
      <!-- First Card -->
      <div class="col">
        <div class="card card1">
          <div class="card-body">
            <img :src="currentContent1.img" class="card-img1" alt="Image 1">
            <p class="card-text">{{ currentContent1.content }}</p>
          </div>
          <div ref="swiper1" class="button-group button-group1 swiper-container">
            <div class="swiper-wrapper">
              <button v-for="(option, index) in contentOptions1" :key="index" class="btn btn-dark swiper-slide" @click="setCurrentContent1(option)">{{ option.title }}</button>
            </div>
          </div>
        </div>
      </div>

      <!-- Second Card -->
      <div class="col">
        <div class="card card2">
          <h1>Udforsk Questen</h1>
          <div class="card-body"> 
            <h2 class="card-title">{{ currentContent2.title }}</h2>
            <p class="card-text">{{ currentContent2.content }}</p>
            <img :src="currentContent2.img" class="card-img" alt="Image 2">
          </div>
          <div ref="swiper2" class="button-group button-group2 swiper-container">
            <div class="swiper-wrapper">
              <button v-for="(option, index) in contentOptions2" :key="index" class="btn btn-dark swiper-slide" @click="setCurrentContent2(option)">{{ option.title }}</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

  
  
<script setup>
import { ref, onMounted } from 'vue';
import Swiper from 'swiper';

import malice from '@/assets/figurer/Malice.png'
import gnist from '@/assets/figurer/gnist.png'
import havfrue from '@/assets/figurer/havfrue.png'
import troldmand from '@/assets/figurer/troldmand.png'
import arkivaren from '@/assets/figurer/arkivaren.png'
import kort from '@/assets/images/kort.jpg'
import drage from '@/assets/images/drage.png'
import hotelb from '@/assets/images/hotelb.jpg'
import arriva from '@/assets/images/arriva.jpg'

const contentOptions1 = ref([
  { title: 'Gnist', img: gnist },
  { title: 'Malice', img: malice },
  { title: 'Havfrue', img: havfrue },
  { title: 'Troldmand', img: troldmand },
  { title: 'arkivaren', img: arkivaren },
]);

const contentOptions2 = ref([
  { title: 'Hvad er det', content: 'Når tusmørket begynder at sænke sig over Esbjerg, skrues sværhedsgraden i AftenQuesten op. Nu skal der virkelig tænkes kreativt. Det kræver mod, samarbejde og snilde. Er du vild med at løse gåder og knække koder, så har du den ultimative mulighed i Questen. Questen tager ca. en time at gennemføre.', img: drage },
  { title: 'Tid & sted', content: 'På torvet i Esbjerg går det løs, fra 18.00-22:30. Tøv ikke og få bestilt den tid, som passer din gruppe.', img: kort },
  { title: 'Trailer', content: '', img: 'path_to_img6' },
  { title: 'Overnatning', content: 'I samarbejde med hotel Britannia, vil du få 10% rabat på overnatning, når du viser din Quest billet', img: hotelb },
  { title: 'Transport', content: 'Der går mange togforbindelser til Esbjerg station. Stationen ligger 100 m fra Torvet, hvor Questen starter.', img: arriva },
]);

const currentContent1 = ref({});
const currentContent2 = ref({});

const setCurrentContent1 = (option) => {
  currentContent1.value = option;
  // Add 'active' class to the clicked button and remove it from others
  contentOptions1.value.forEach((item, index) => {
    const button = document.querySelector(`.button-group1 .btn:nth-child(${index + 1})`);
    if (button) {
      if (item.title === option.title) {
        button.classList.add('active');
      } else {
        button.classList.remove('active');
      }
    }
  });
};

const setCurrentContent2 = (option) => {
  currentContent2.value = option;
  // Add 'active' class to the clicked button and remove it from others
  contentOptions2.value.forEach((item, index) => {
    const button = document.querySelector(`.button-group2 .btn:nth-child(${index + 1})`);
    if (button) {
      if (item.title === option.title) {
        button.classList.add('active');
      } else {
        button.classList.remove('active');
      }
    }
  });
};

onMounted(() => {
  if (window.innerWidth < 800) {
    new Swiper('.swiper-container', {
      slidesPerView: 'auto',
      spaceBetween: 10,
    });
  }
});

// Load the content of the first button by default
setCurrentContent1(contentOptions1.value[0]);
setCurrentContent2(contentOptions2.value[0]);
</script>

  
  <style lang="scss" scoped>
  @import '@/assets/hexcolors.scss';
  
  .container {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 5%;
    text-align: center;
    margin-top: 10%;
  }
  
  .row {
    display: flex;
    flex-wrap: wrap;
    width: 150%;
    justify-content: space-around;
  }
  
  .col {
    flex: 1 1 45%;
    margin: 10px;
    display: flex;
    justify-content: center;
  }
  
  h1 {
    color: $primary-yellow;
  }
  p{
    text-align: start;
  }
  
  .card {
  position: relative;
  width: 100%;
  height: 60%;
  border: none;
  border-radius: 30px;
  background: linear-gradient(to bottom, $secondary-purple, $primary-purple);
  color: #fff;
  padding: 20px;
}

  .card-img {
    width: 100%;
    height: auto;
    border-radius: 20px;
  }
  
  .card-img1 {
    width: 100%;
  }
  
  .button-group {
    width: 40%;
    position: absolute;
    display: flex;
    flex-direction: column;
    z-index: 3;
  }
  
  .button-group1 {
    top: 60%;
    left: -20%;
    align-items: end;
  }
  
  .button-group2 {
    top: 60%;
    right: -20%;
    align-items: end;
  }
  
  .btn {
  margin: 5px 0;
  background-color: rgba(13, 81, 13, 0.547); /* Example color */
  border: none;
  padding: 5px 3px;
  width: 100%;
  transition: opacity 0.2s ease; /* Smooth transition for opacity changes */
}

.btn.active {
  opacity: 1;
  background-color: $primary-green; /* Full opacity for active button */
}

  
  .card1 {
    transition: transform 0.3s ease;
  }
  
  .card2 {
    transition: transform 0.3s ease;
  }
  
  .button-group1,
  .button-group2 {
    transition: transform 0.3s ease;
  }
  
  .button-group1:hover,
  .button-group2:hover {
    transform: translateY(-5px); /* Move button group up on hover */
  }
  
  @media (max-width: 800px) {
    .container{
      padding: 0;
    }
    .card{
      width: 200%;
      margin-top: 50%;
      margin-left: -5%;
    }
    .card-img1 {
    width: 140%;
    margin-top: -50%;
    margin-left: -20%;
  }
    .row {
      flex-direction: column; /* Stack cards vertically on smaller screens */
    }
  
    .button-group {
      flex-direction: row;
      overflow: hidden;
      white-space: nowrap;
      padding: 10px 0;
      /* Hide the scrollbar */
      -ms-overflow-style: none; /* IE and Edge */
      scrollbar-width: none; /* Firefox */
    }
    
    .button-group::-webkit-scrollbar {
      display: none; /* Chrome, Safari, and Opera */
    }
  
    .btn {
      position: relative;
      flex: 0 0 auto; /* Prevents buttons from shrinking */
      width: 20%;
      margin: 0 5px;
    }
  
    .button-group {
      right: 0%;
      bottom: -40%;
      align-items: center;
      width: 100%;
  
    }
    .button-group1 {
      margin-left: 20%;
  
    }
  
  
  }
  </style>