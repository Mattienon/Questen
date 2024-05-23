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

.body {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100%;
}


/* Add more styles as needed for other sections */
</style>
