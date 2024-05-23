<template> 
  <div class="position">
    <footer class="footer">
      <div class="greenfoot">  
        <div class="btn btn-dark"><span>Fantasy Festival</span></div>
        <span class="text">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Numquam itaque sint natus, libero.</span>
      
      </div>
      
      <div class="whiteframe">
        <div class="navigation-links">
          <span class="copyright">@Copyright Quest 2024</span>
          <RouterLink
            v-for="(link, index) in navigationLinks"
            :key="index"
            :to="link.path"
            class="footer-link"
          >{{ link.text }}</RouterLink>
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
import { RouterLink } from 'vue-router';

const navigationLinks = ref([
  { path: '/', text: 'Privacy Policy' },
  { path: '/About', text: 'Terms of Service' }
]);
</script>

<style lang="scss" scoped>
@import '@/assets/hexcolors.scss';

.position {
  display: flex;
  flex-direction: column;
  margin-top: 5%;
  z-index: 1000;
  width: 100%;
}

.footer {
  margin-top: auto; /* Pushes the footer to the bottom */
  display: flex;
  flex-direction: column;
  background-color: $primary-green;
  position: relative;
  bottom: 0; /* Set the footer at the bottom */
  width: 100%; /* Make sure the footer spans the full width */
}

.greenfoot {
  width: 80%;
  padding: 20px; /* Added padding for better spacing */
  margin-top: 2%;
  margin-left: 1.5%;
  display: flex;
  justify-content: center; /* Align items evenly */
  align-items: center; /* Vertically center items */
  background-color: $primary-green;
}
.text {
  padding-left: 1rem;
  color: white; /* Change text color to white for better visibility */
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

.footer-link {
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
  border-radius: 25px; /* Reduced border radius for a more subtle appearance */
  width: 200px; /* Increased button width for better clickability */
  padding: 10px; /* Added padding for better button appearance */
  background-color: $primary-yellow;
  border: none;
  color: black;
  font-weight: bold;
  text-align: center; /* Center align text */
  cursor: pointer; /* Add pointer cursor on hover for better UX */
  transition: background-color 0.3s ease; /* Smooth transition on hover */
}

.btn:hover {
  background-color: darken($primary-yellow, 10%); /* Darken button color on hover */
}
.footerimg {
  width: 22%;
  position: absolute;
  right: 2%;
  bottom: 0%;
  z-index: 1;
  pointer-events: none;
}

@media (max-width: 800px) {
  .footerimg {
    position: absolute;
    right: -5%;
    bottom: 0%;
  }

  .btn, .title {
    display: flex;
    align-items: center;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 50px;
    width: 40%;
    margin: auto;
  }

  .greenfoot {
    width: 90%;
    padding-left: 3%;
    margin-top: 10%;
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
