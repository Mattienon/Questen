<template>
  <div class="home-view body">
    <drage />
    <div class="logoarea">
      <logoarea />
    </div>
    <div class="outerim">
      <div class="info-boxes">
        <infoboxes />
      </div>
      <div class="heroarea">
        <hero />
      </div>
      <div class="questcard">
        <div class="questtekst">
          <h1>{{ intro }}</h1>
          <p>{{ brødtekst }}</p>
          <span>{{ xtra }}</span>
        </div>
      </div>
      <div class="trailer">
        <trailer />
      </div>
      <hr class="hrline">
      <additionalinfo />
      <div class="bottom-card">
        <bottomcard />
      </div>
    </div>
    <footnav />
  </div>
</template>

<script setup>
import { ref } from 'vue';

const intro = ref('Men hvad er questen?');

const brødtekst = ref(`
Questen er en kombination af elementer fra ”Fangerne på Fortet”, teater og rollespil/DnD. 
Denne begivenhed er arrangeret i både en børnevenlig version om dagen og en mere intens voksen-version om aftenen. 
Festivalen tilbyder en unik mulighed for at træde ind i en anden virkelighed, hvor grænserne mellem virkelighed og fiktion bliver udvisket. 
Questen er et oplevelsesløb, som varer ca. en time, og der bliver afholdt flere på samme aften.
The Quest er en ukendt begivenhed, da den først er blevet planlagt nu. 
Derfor vil vi i denne opgave udarbejde en løsning på, hvordan vi får så mange som muligt ind og opleve denne fantastiske verden.`);

const xtra = ref('Ikke nok med det Fantasy Quest er i samarbejde med Dystopia!');

import additionalinfo from '../components/HomeView/additionalinfo.vue';
import hero from '@/components/HomeView/hero.vue';
import bottomcard from '@/components/HomeView/bottomcard.vue';
import logoarea from '@/components/HomeView/logoarea.vue';
import infoboxes from '@/components/HomeView/infoboxes.vue';
import footnav from '@/components/Essentials/footnav.vue';
import trailer from '@/components/HomeView/trailer.vue';
import drage from '@/components/Essentials/drageanim.vue';
</script>

<style lang="scss" scoped>
@import '@/assets/hexcolors.scss';

.home-view {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin: auto;
  z-index: 10;
}

.info-boxes {
  margin-top: 5%;
}

.questcard {
  background: linear-gradient(to bottom, $secondary-purple 30%, $light-purple 75%, transparent);
  margin: 5%;
  margin-top: -15%;
  padding-top: 15%;
  border-radius: 20px;
}

.questtekst, p, h1, span {
  width: 90%;
  margin: 5%;
  line-height: 30px;
}

.questtekst, h1, span {
  color: white;
  font-weight: 900;
  letter-spacing: 3px;
}

.trailer {
  width: 100%;
  margin-top: -12%;
  margin-bottom: 5%;
}

.heroarea {
  margin-top: 5%;
  width: 100%;
}

.bottom-card {
  width: 100%;
  z-index: 2;
  padding-bottom: 8%;
  padding-top: 8%;
}

.logoarea {
  margin-top: 5%;
  margin-bottom: -10%;
  z-index: 11;
}

$notchSize: 15px;

.outerim {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: relative;
  width: 88%;
  margin-top: 0%;
  z-index: 1;
  border: 10px outset $primary-yellow;
  background: linear-gradient(to bottom, $light-purple -70%, $primary-purple 50% 83%, $primary-green 96%);
  clip-path: polygon(
    0% $notchSize, 
    $notchSize 0%, 
    calc(100% - #{$notchSize}) 0%, 
    100% $notchSize, 
    100% calc(100% - #{$notchSize}), 
    calc(100% - #{$notchSize}) 100%, 
    $notchSize 100%, 
    0% calc(100% - #{$notchSize})
  );
}

// Media queries

@media (max-width: 800px) {
  .info-boxes, .additional-info, .logo-area{
    align-items: center;
    margin: auto;
    width: 85%;
    padding: 2%;
    padding-bottom: 30%;
  }
  .outerim {
    margin-top: -20%;
    width: 95%;
  }

  .logoarea {
    display: flex;
    justify-content: center;
    align-items: center;
  }
}

@media (max-width: 360px) {
  .logoarea{
    padding: 10%;
  }
  .outerim {
    margin-top: -30%;
    width: 95%;
  }
  .info-boxes, .additional-info {
    align-items: center;
    margin: auto;
    width: 85%;
    padding: 0;
    margin-bottom: 20%;
  }
  .trailer{
  margin-bottom: 20%;
}
}
</style>

