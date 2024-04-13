<template>
    <div class="gallery">
      <div class="image-container" v-for="(image, index) in paginatedImages" :key="index">
        <img :src="image.src" :alt="image.alt">
        <div class="product-info">
          <p>{{ image.name }}</p>
          <span>Już od: {{ image.price }}</span>
        </div>
      </div>
    </div>
      <div class="pagination">
    <select v-model="imagesPerPage">
      <option value="4">4</option>
      <option value="8">8</option>
      <option value="12">12</option>
      <option value="16">16</option>
    </select>
        <button @click="prevPage" :disabled="currentPage === 0">Previous</button>
        <button @click="nextPage" :disabled="currentPage >= maxPage">Next</button>
      </div>
  </template>
  
  <script>
  import { ref, computed, watch } from 'vue';
  
  export default {
    name: 'ImageGallery',
    props: ['images'],
    setup(props) {
      const imagesPerPage = ref(8);  
      const currentPage = ref(0);
  
      const paginatedImages = computed(() => {
        const start = currentPage.value * Number(imagesPerPage.value); 
        const end = start + Number(imagesPerPage.value); 
        return props.images.slice(start, end); 
      });
  
      const maxPage = computed(() => Math.ceil(props.images.length / Number(imagesPerPage.value)) - 1);
  
      const prevPage = () => {
        if (currentPage.value > 0) {
          currentPage.value--;
        }
      };
  
      const nextPage = () => {
        if (currentPage.value < maxPage.value) {
          currentPage.value++;
        }
      };
  
      watch(imagesPerPage, () => {
        currentPage.value = 0;
      });
  
      return { currentPage, imagesPerPage, paginatedImages, prevPage, nextPage, maxPage };
    }
  };
  </script>
  
  
  <style scoped>
  .gallery {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 1rem;
  }
  
  .image-container {
    flex: 0 1 calc(25% - 1rem);
  }
  
  .pagination {
    display: flex;
    justify-content: center;
    margin-top: 1rem;
    margin-bottom: 3rem;
  }
  
  .pagination button {
    margin: 0 0.5rem;
  }
  
  .product-info {
    text-align: left;
    font-size: 1.5rem;
    line-height: 1.2;
    font-weight: 600;
  }
  
  .product-info span {
    font-size: 1.4rem;
    font-weight: 400;
    line-height: 1.42857143;
  }
  </style>
  