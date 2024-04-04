<script>
const promos = [
  { title: "outlet", description: 'Wyprzedaz 2023', imgPath: "promo1.png", ctaText: "zobacz" },
  { title: "kolekcja 2020", description: 'Nowa kolekcja', imgPath: "promo2.png", ctaText: "zobacz" },
]
import PromoItem from './PromoItem.vue'

export default {
  data() {
    return {
      promos,
    }
  },
  components: {
    PromoItem,
  }
}
</script>
<template>
  <div style="width: 100%;flex:1;">
  <h2 class="header">Promocje</h2>
  <div class="promoContainer">
    <PromoItem v-bind:promoItem="promoItem" v-for="promoItem in promos" />
  </div>
  </div>
</template>
<style scoped>
  .promoContainer {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 0 8px;
    gap: 16px;
  }
  .header {
    text-align: center;
    margin: 1em 0;
    font-size: 2em;
    font-weight: 700;
    color: #000;
  }
</style>