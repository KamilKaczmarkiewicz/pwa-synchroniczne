<script>
const info = [
  { icon: 'discount', title: "SKORZYSTAJ Z PROMOCJI", description: "Odwiedzając naszą stronę zawsze możesz liczyć na ciekawe promocje" },
  { icon: 'shoppingbag', title: "WYSYŁKA", description: "Gwarantujemy wysyłkę w ciągu 24h od zaksięgowania płatności" },
  { icon: 'privacy', title: "BEZPIECZNE ZAKUPY", description: "Kupując w naszym sklepie masz gwarancję bezpiecznych zakupów i płatności" },
]
import InfoItem from './InfoItem.vue'

export default {
  data() {
    return {
      info,
    }
  },
  components: {
    InfoItem,
  }
}
</script>
<template>
  <div class="infoContentContainer">
    <InfoItem v-bind:infoItem="infoItem" v-for="infoItem in info" />
  </div>
</template>
<style scoped>
  .infoContentContainer {
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: #f9f7f4;
    gap: 12em;
    padding: 4em 12em;
  }
</style>