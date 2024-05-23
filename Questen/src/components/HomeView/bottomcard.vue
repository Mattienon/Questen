<template>
  <div class="card">
    <div class="cardtitle">
      <h1>Questen er et uendeligt eventyr</h1>
    </div>
    <div class="cardcontent">
      <h2>Nyt hvert år</h2>
      <span class="text">Skriv dig op til opdateringer om kommende Quest nyheder og Events</span>
      <!-- Email sign-up form -->
      <form class="signup-form" @submit.prevent="submitForm" novalidate>
        <label for="email" class="visually-hidden">Email</label>
        <input type="email" id="email" v-model="email" placeholder="Indtast din email" required aria-required="true">
        <button type="submit" class="btn btn-dark"><span>Tilmeld</span></button>
      </form>
      <!-- Success message -->
      <p v-if="submitted" class="success-message">Tak for din tilmelding!</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const email = ref('');
const submitted = ref(false);

const submitForm = () => {
  // Simulate form submission (replace with actual submission logic)
  if (email.value) {
    console.log('Email submitted:', email.value);
    submitted.value = true;
    // Reset form after submission
    email.value = '';
    setTimeout(() => {
      submitted.value = false;
    }, 3000); // Hide success message after 3 seconds
  }
};
</script>

<style lang="scss" scoped>
@import '@/assets/hexcolors.scss';

.cardtitle, .cardcontent{
  padding: 0.1rem;
  color: $primary-yellow;
}
.text{
  font-style: oblique;
  color: black;
}

/* Add visually hidden class for accessibility */


.card {
  background-color: $light-purple;
  margin: 0 auto; /* Center the card */
  outline: none;
  border: none;
  text-align: center;
  display: flex;
  flex-direction: column; /* Ensure content stacks vertically */
  justify-content: center; /* Vertically center content */
  align-items: center; /* Horizontally center content */
  padding: 20px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2); /* Add shadow to card */
  transition: box-shadow 0.3s ease; /* Smooth transition for shadow change */
}

.card:hover {
  box-shadow: 0 2px 2px rgba(0, 0, 0, 0.3); /* Intensify shadow on hover */
}

.signup-form {
  display: flex; /* Use flexbox layout */
  justify-content: center; /* Align form elements horizontally */
  align-items: center; /* Align items vertically */
  flex-wrap: wrap; /* Allow wrapping */
  gap: 10px; /* Add gap between elements */
  margin-top: 20px;
}

.signup-form input[type="email"] {
  flex: 1; /* Take up remaining space */
  padding: 10px;
  border-radius: 5px;
  border: none;
  font-size: 1rem;
}

.signup-form button {
  padding: 11px 20px;
  border: none;
  background-color: $primary-purple;
  color: #fff;
  border-radius: 5px;
  cursor: pointer;
  font-size: 1rem;
}

.signup-form button:hover {
  background-color: lighten($primary-yellow, 2%);
}

.success-message {
  color: black;
  margin-top: 10px;
}

@media (max-width: 800px) {
  .card {
    width: 90%;
  }
  .signup-form {
    width: 100%;
  }
}

@media (max-width: 600px) {
  .cardtitle, h1{
    display: none;
  }
  .signup-form input[type="email"], .signup-form button {
    font-size: 0.9rem;
  }
}
</style>
