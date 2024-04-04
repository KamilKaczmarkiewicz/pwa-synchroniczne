<script setup>
  const props = defineProps(['promoItem'])
</script>

<template>
  <div style="position: relative;">
    <img :src="promoItem.imgPath" class="img" />
    <div class="details">
      <p class="detailTitle">{{ promoItem.title }}</p>
      <p class="description">{{ promoItem.description }}</p>
      <div class="btn">
        <p>{{ promoItem.ctaText }}</p>
        <i-arrowright class="icon"/>
      </div>
    </div>
  </div>
</template>

<style scoped>
  .itemContainer {
    position: relative;
  }
  .img {
    object-fit: cover;
  }
  .details {
    position: absolute;
    bottom: 44px;
    left: 31px;
  }
  .detailTitle {
    color: #fff;
    text-transform: uppercase;
    letter-spacing: 2.3px;
    font-size: 0.9rem;
    margin-bottom: 88px;
  }
  .description {
    font-size: 10px;
  }
  .btn {
    width: 8em;
    cursor: pointer;
    background: #000;
    color: #fff;
    border: 1px solid #000;
    display: flex;
    align-items: center;
    justify-content: space-around;
    transition: all 0.2s ease-in-out;
  }
  .btn:hover {
    background: #fff;
    color: #000;
  }
  .btn:hover>.icon {
    color: #000;
  }
  .icon {
    color: #fff;
    transition: all 0.2s ease-in-out;
  }
</style>