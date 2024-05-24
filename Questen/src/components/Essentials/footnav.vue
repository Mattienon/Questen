<template>
  <div class="position">
    <footer class="footer">
      <div class="greenfoot">
        <div class="btn btn-dark"> 
  <a href="https://fantasyfestival.dk/"><span>Fantasy Festival</span></a>
</div>

        <span class="text">
          <h1>Kontakt os</h1>
          <p>Fantasyfestival@esbjerg.dk</p>
          <p>79 000000</p>
        </span>
      </div>

      <div class="whiteframe">
        <div class="navigation-links">
          <span class="copyright">@Copyright Quest 2024</span>
        
          <a
            v-for="(link, index) in navigationLinks"
            :key="index"
            :href="link.path"
            class="footer-link"
          >{{ link.text }}</a>
        </div>
      </div>

      <div class="footerimg">
        <img src="@/assets/images/raven.svg" alt="Raven Image">
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const navigationLinks = ref([
  { path: 'https://www.universe.com/events/fantasy-quest-aftenquest-tickets-2PCHR4', text: 'Billetter' },
  { path: '/', text: 'Det med småt' }
]);
</script>

<style lang="scss" scoped>
@import '@/assets/hexcolors.scss';

.position {
  display: flex;
  margin-top: 5%;
  z-index: 10;
  width: 100%;
}

.footer {
  margin-top: auto; 
  display: flex;
  flex-direction: column;
  background-color: $primary-green;
  position: relative;
  bottom: 0; 
  width: 100%; 
  border-top-left-radius: 100px; 
  border-top-right-radius: 100px;
}

.greenfoot {
  width: 70%;
  padding: 10px;
  margin-top: 2%;
  margin-left: 2%;
  display: flex;
  justify-content: start; 
  align-items: center; 
}

.text {
  font-size: 25px;
  margin-bottom: 15px;
  color: rgb(0, 0, 0); 
}

.text p {
  font-size: 18px;
  color: white;
}

.whiteframe {
  background-color: white;
  width: 95%;
  text-align: center;
  margin: auto;
  margin-bottom: 1%;
}

.navigation-links {
  display: flex;
  justify-content: space-evenly;
  padding: 8px 0;
}

.footer-link{
  color: $primary-yellow;
  text-decoration: none;
  display: flex;
  justify-content: flex-end;
}

.title, .text {
  font-size: large;
  margin-bottom: 0.5rem;
}

.btn {
  border-radius: 25px; 
  width: 200px; 
  padding: 10px; 
  background-color: $primary-yellow;
  border: none;
  color: black;
  font-weight: bold;
  text-align: center; /* Center align text */
  cursor: pointer; /* Add pointer cursor on hover for better UX */
  transition: background-color 0.3s ease; /* Smooth transition on hover */
  margin-right: 250px;
  margin-bottom: 20px;
}

.btn:hover {
  background-color: darken($primary-yellow, 10%); /* Darken button color on hover */
}

.footerimg {
  width: 22%;
  position: absolute;
  right: 2%;
  bottom: 0%;
  pointer-events: none;
}

a{
  text-decoration: none;
  color: black;
}
@media (max-width: 1000px) {
  .footerimg {
    position: absolute;
    right: -5%;
    bottom: 0%;
  }

  .btn, .title {
    display: flex;
    align-items: start;
    justify-content: center;
    border-radius: 50px;
    width: 40%;
    margin: auto;
  }

  .greenfoot {
    width: 90%;
    padding-left: 3%;
    margin-top: 5%;
  }

  .whiteframe {
    background-color: white;
    text-align: center;
  }

  .copyright, .text{
    display: none; /* Hide the span on smaller screens */
  }
}

@media (max-width: 400px) {
  .footerimg {
    width: 50%;
    position: absolute;
    right: -18%;
    bottom: 10%;
  }

  .copyright, .text{
    display: none; /* Hide the span on smaller screens */
  }
}
</style>
