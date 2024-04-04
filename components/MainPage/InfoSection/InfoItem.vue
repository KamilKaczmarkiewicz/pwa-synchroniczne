<script setup lang="ts">
  const props = defineProps(['infoItem'])
</script>

<template>
  <div class="infoContainer">
    <i-discount v-if="infoItem.icon === 'discount'" class="icon"/>
    <i-privacy v-else-if="infoItem.icon === 'privacy'" class="icon"/>
    <i-shoppingbag v-else-if="infoItem.icon === 'shoppingbag'" class="icon"/>
    <p class="infoTitle">{{ infoItem.title }}</p>
    <p>{{ infoItem.description }}</p>
  </div>
</template>

<style scoped>
  .infoContainer {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
  .infoTitle {
    margin: 1em 0;
  }
  .icon {
    font-size: 72px;
    color: #000;
  }
</style>