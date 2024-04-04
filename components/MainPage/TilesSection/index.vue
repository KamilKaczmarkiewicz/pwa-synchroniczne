<script>
import Tile from './Tile.vue'
export default {
  data() {
    return {
      tileImagePaths: ["1.png", "2.png", "3.png", "4.png"],
    }
  },
  components: {
    Tile,
  }
}
</script>

<template>
  <div class="containersss">
    <div v-for="imgPath in tileImagePaths">
      <Tile v-bind:imgpath="imgPath"/>
    </div>
  </div>
</template>

<style scoped>
  .containersss {
    display: flex;
    justify-content: space-around;
    align-items: center;
    margin: 8em 16em;
  }
</style>


