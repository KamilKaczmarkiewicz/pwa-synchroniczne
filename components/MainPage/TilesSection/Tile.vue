<script setup>
const props = defineProps(['imgpath'])
</script>

<template>
  <a>
    <img :src="imgpath" class="container" />
  </a>
</template>

<style scoped>
  .container {
    width: 100%;
    height: 163px;
    object-fit: scale-down;
    transition: all 0.2s ease-in-out;
  }
  .container:hover {
    transform: scale(1.2);
  }
</style>
