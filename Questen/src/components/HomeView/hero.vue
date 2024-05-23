<template>
  <div>
      <div class="card" @mouseover="cardHover(true)" @mouseleave="cardHover(false)">
          <div class="cardtitle">
              <h1>Questen starter om</h1>
          </div>
          <div class="cardcontent">
              <countdown/>
          </div>
      </div>
  </div>
</template>

<script setup>
import countdown from '@/components/HomeView/countdown.vue';
</script>

<style lang="scss" scoped>
@import '@/assets/hexcolors.scss';

h1 {
  color: $primary-yellow;
  font-size: 8vw;
  margin: 0;
}

a {
  text-decoration: none;
  color: $primary-yellow;
  font-weight: bold;
  cursor: pointer;
}

.card {
  background-color: $light-purple;
  height: 100%;
  max-height: 350px;
  width: 100%;
  outline: none;
  border: none;
  text-align: center;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  box-shadow: 0 80px 100px rgba(0, 0, 0, 0.2);
  transition: box-shadow 0.3s ease;
  margin: auto;
  padding: 1rem;
}

 
@media (max-width: 560px) {
    .h1{
      font-size: 20rem;
    }

  }
    

/* Hover effect */
.card:hover {
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.3); /* Change box shadow on hover */
}
</style>
