<template>
  <div class="maincontent">
    <PageTitle />
    <ImageGallery :images="images" />
  </div>
</template>

<script>
import { ref, computed, onMounted, onUnmounted, watchEffect } from 'vue';
import PageTitle from '../components/DailyStylesPage/PageTitle'
import ImageGallery from '../components/DailyStylesPage/ImageGallery'


export default {
  name: 'stylizajceCodzienne',
  components: {
    PageTitle,
    ImageGallery,
  },
  setup() {
    const imagesPerPage = ref(8); // Default images per row
    const currentPage = ref(0);
    const images = ref([
    { src: '/images2/1.jpg', alt: 'Logo 1', name: 'Product Name 1', price: '100.00'  },
    { src: '/images2/2.jpg', alt: 'Logo 2', name: 'Product Name 1', price: '100.00'  },
    { src: '/images2/3.jpg', alt: 'Logo 3', name: 'Product Name 1', price: '100.00'  },
    { src: '/images2/4.jpg', alt: 'Logo 4', name: 'Product Name 1', price: '100.00'  },
    { src: '/images2/5.jpg', alt: 'Logo 5', name: 'Product Name 1', price: '100.00'  },
    { src: '/images2/6.jpg', alt: 'Logo 6', name: 'Product Name 1', price: '100.00'  },
    { src: '/images2/7.jpg', alt: 'Logo 7', name: 'Product Name 1', price: '100.00'  },
    { src: '/images2/8.jpg', alt: 'Logo 8', name: 'Product Name 1', price: '100.00'  },
    { src: '/images2/9.jpg', alt: 'Logo 9', name: 'Product Name 1', price: '100.00'  },
    { src: '/images2/10.jpg', alt: 'Logo 10', name: 'Product Name 1', price: '100.00'  },
    { src: '/images2/11.jpg', alt: 'Logo 11', name: 'Product Name 1', price: '100.00'  },
    { src: '/images2/12.jpg', alt: 'Logo 12', name: 'Product Name 1', price: '100.00'  },
    { src: '/images2/13.jpg', alt: 'Logo 13', name: 'Product Name 1', price: '100.00'  },
    { src: '/images2/14.jpg', alt: 'Logo 14', name: 'Product Name 1', price: '100.00'  }
    ]);


    const paginatedImages = computed(() => {
      const start = currentPage.value * imagesPerPage.value;
      console.log(start);
      return images.value.slice(start, start + imagesPerPage.value);
    });

    const maxPage = computed(() => {
      return Math.ceil(images.value.length / imagesPerPage.value) - 1;
    });

    const prevPage = () => {
      if (currentPage.value > 0) currentPage.value--;
    };

    const nextPage = () => {
      if (currentPage.value < maxPage.value) currentPage.value++;
    };

    watchEffect(() => {
      // Reset to the first page if the images per page changes
      currentPage.value = 0;
    });

    return { currentPage, images, paginatedImages, prevPage, nextPage, maxPage, imagesPerPage };
  }
};
</script>

<style scoped>
.maincontent {
  box-sizing: border-box;
    margin-left: auto;
    margin-right: auto;
    max-width: 1140px;
    padding-left: 40px;
    padding-right: 40px;
}
.gallery {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 1rem;
}

.image-container {
  flex: 0 1 calc(25% - 1rem); /* Adjust number based on the number of images per row */
}

.pagination {
  width: 100%;
  display: flex;
  justify-content: center;
  margin-top: 1rem;
}

.pagination button {
  margin: 0 0.5rem;
}

.product-info {
  text-align: left;
}

.product-info p {
    display: block;
    font-size: 1.5rem;
    line-height: 1.2;
    font-weight: 600;
    color: #000;
    margin: 0 0 5px;
    letter-spacing: .3px;
}

.product-info span {
    font-size: 1.4rem;
    font-style: normal;
    font-weight: 400;
    line-height: 1.42857143;
}

.page-title-wrapper {
    padding-top: 30px;
    margin-bottom: 30px;
    box-sizing: border-box;
    display: block;
    unicode-bidi: isolate;

}

.page-title {
    margin-block-start: 0.67em;
    margin-block-end: 0.67em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
    font-size: 2.4rem;
    line-height: 1.2;
    margin: 0;
    font-weight: 600;
    text-transform: uppercase;

}


@media (max-width: 599px) {
  .image-container {
    flex: 0 1 calc(50% - 1rem);
  }
}

@media (min-width: 600px) and (max-width: 899px) {
  .image-container {
    flex: 0 1 calc(33.333% - 1rem);
  }
}

/* No media query needed for larger screens since it's the default */
</style>
