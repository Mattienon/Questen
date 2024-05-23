<template>
    <div class="body">
      <gallery/>
      <!-- Gallery is the imported component with the Gallery structure -->
    </div>
 
</template>

<script setup>
import gallery from '@/components/Gallery/gallery.vue';

</script>

<style lang="scss" scoped>
.home-view {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background-color: aqua;
  width: 100%;
}

.hero-area {
  background-color: red;
}

/* Add more styles as needed for other sections */
</style>
