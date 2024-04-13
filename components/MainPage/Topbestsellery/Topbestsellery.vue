<template>
    <div class="top-bestsellers">
        <div class="title"><span>Top Bestsellery</span></div>
        <p class="title2">Najczêœciej wybierane produkty przez naszych klientów</p>
        <div class="products">
            <div class="product-container">
                <div class="bestsellers-text">Bestsellery</div>
                <div v-for="(product, index) in bestsellers" :key="index" class="product"
                     @mouseover="handleMouseOver(index)"
                     @mouseleave="handleMouseLeave()">
                    <nuxt-link :to="`${product.link}`">
                        <img :src="product.image" :alt="product.name" class="product-image" :style="{ marginTop: getImageMarginTop(index) }" />
                    </nuxt-link>
                    <div class="product-image-container">
                        <div v-if="index === hoveredProductIndex" class="sizes-info-container">
                            <div class="sizes-grid">
                                <div v-for="(size, sizeIndex) in product.sizes" :key="sizeIndex" class="size-box">
                                    {{ size }}
                                </div>
                            </div>
                            <div class="favorite-container">
                                <nuxt-link to="https://clickfashion.pl/wishlist/">
                                    <div class="favorite-box">
                                        <img src="~/assets/heart.png" alt="Favirite" class="favorite-icon">
                                    </div>
                                </nuxt-link>
                            </div>
                        </div>
                    </div>
                    <div class="product-details">
                        <nuxt-link :to="`${product.link}`" class="product-name-link">
                            <p class="product-name">{{ product.name }}</p>
                        </nuxt-link>
                        <p class="product-oldprice">{{ product.oldprice }}</p> <p class="product-price">{{ product.price }}</p>
                    </div>
                </div>
                <div class="bestseller-link-container">
                    <nuxt-link to="https://clickfashion.pl/nowosci.html">
                        <div class="bestseller-link-btn">
                            <a class="bestseller-link">
                                <span class="button-text">ZOBACZ WIÊCEJ</span>
                                <ArrowSvg class="arrow-icon" />
                            </a>
                        </div>
                    </nuxt-link>
                </div>
            </div>
        </div>
    </div>
</template>

<script>import ArrowSvg from "~/assets/arrow.svg";
export default {
    components: {
        ArrowSvg,
    },
    data() {
        return {
            bestsellers: [
                {
                    id: 1,
                    link: 'https://clickfashion.pl/70-657.html',
                    name: 'Marynarka Ala Stripes',
                    image: 'https://clickfashion.pl/media/catalog/product/cache/fb6c9e4c0a5b32f84e18ba5122e0ff98/c/l/click_1011_9575_kopia.jpg',
                    oldprice: '599,00 z³',
                    price: '599,00 z³',
                    sizes: ['36', '38', '40', '42', '44']
                },
                {
                    id: 2,
                    link: 'https://clickfashion.pl/70-950.html',
                    name: 'Marynarka Nana',
                    image: 'https://clickfashion.pl/media/catalog/product/cache/fb6c9e4c0a5b32f84e18ba5122e0ff98/4/1/41de079b69334e36a2e3a33818e4bbc1.jpg',
                    oldprice: '549,00 z³',
                    price: '549,00 z³',
                    sizes: ['36', '38', '40', '42', '44', '46']
                },
                {
                    id: 3,
                    link: 'https://clickfashion.pl/30-261.html',
                    name: 'Spodnie Nana',
                    image: 'https://clickfashion.pl/media/catalog/product/cache/fb6c9e4c0a5b32f84e18ba5122e0ff98/3/0/30-261_3_.jpg',
                    oldprice: '299,00 z³',
                    price: '299,00 z³',
                    sizes: ['38', '40', '42', '44', '46']
                },
            ],
            hoveredProductIndex: -1,
            sizesContainer: null,
        }
    },
    methods: {
      getImageMarginTop(index) {
    const marginTopMap = {
        0: '120px',
        1: '0px',
        2: '250px',
    };

    return marginTopMap[index] || '0';
  },

      handleMouseOver(index) {
        this.hoveredProductIndex = index;
        this.$nextTick(() => {
            this.sizesContainer = document.querySelector('.sizes-info-container');
            if (this.sizesContainer) {
                const sizesCount = this.sizesContainer.querySelectorAll('.size-box').length;
                const sizeBoxHeight = 50;
                this.sizesContainer.style.height = `${sizesCount * sizeBoxHeight}px`;
            }
        });
      },

        handleMouseLeave() {
        this.hoveredProductIndex = -1;
          if (this.sizesContainer) {
            this.sizesContainer.style.height = '0';
          }
      }
  }


}</script>

<style scoped>


    .top-bestsellers {
        text-align: center;
    }

    .title {
        font-family: "Montserrat", sans-serif;
        font-size: 36px;
        font-weight: 700;
        flex: 1 0 100%;
        line-height: 1.2;
        color: #000;
        letter-spacing: 1.2px;
        margin-bottom: 20px;
        padding-top: 61px;
        border-top: 1px solid #f5f5f5;
        width: 100%;
    }

    .title2 {
        margin-bottom: 50px;
    }

    .products {
        margin-left: 150px;
        margin-right: 150px;
        margin-bottom: 100px;
    }

    .product {
        display: inline-block;
        margin: 10px;
        vertical-align: top;
        width: 30%;
        height: auto;
    }

    .product-name:hover {
        text-decoration: underline;
        color: white;
    }

    .product-image {
        max-width: 100%;
        box-shadow: 9px 5px 50px rgba(0,0,0,.2);
        position: relative;
        display: block;
    }

    .product-details {
        padding: 18px 0 0;
        font-family: Arial;
        text-align: left;
    }

    .product-name {
        font-weight: bold;
        font-weight: 600;
        margin: 0 0 5px;
        color: #000;
    }

    .product-name-link {
        text-decoration: none;
    }

    .product-name:hover {
        text-decoration: underline;
    }

    .product-oldprice {
        float: left;
        margin-right: 5px;
        color: #9a9a9a;
        text-decoration: line-through;
    }

    .product-container {
        position: relative;
        margin-right: auto;
        margin-left: auto;
        max-width: 1800px;
    }

    .bestsellers-text {
        position: absolute;
        font-family: 'Montserrat',sans-serif;
        font-weight: 700;
        line-height: 1.2;
        color: #000;
        opacity: .05;
        left: 0;
        top: 50%;
        transform: translateY(30%);
        font-size: 200px;
    }

    .bestseller-link-container {
        text-align: left;
        margin-left: 30px;
    }

    .bestseller-link-btn {
        text-align: left;
        background-color: white;
        border: 2px solid black;
        display: inline-flex;
        align-items: center;
        justify-content: center;
        padding: 10px 20px;
        transition: background-color 0.3s, color 0.3s, border-color 0.3s;
        display: inline-block;
    }

        .bestseller-link-btn a {
            color: black;
            text-decoration: none;
            text-transform: uppercase;
            font-family: "Montserrat", sans-serif;
            font-weight: 700;
            letter-spacing: 1.83px;
            font-size: 10px;
            display: flex;
            align-items: center;
        }

    .arrow-icon {
        width: 20px;
        height: 20px;
        fill: black;
        transition: fill 0.3s, transform 0.3s;
        filter: drop-shadow(0 0 2px rgba(255, 255, 255, 0));
    }

    .button-text {
        margin-right: 75px;
    }

    .bestseller-link-btn:hover .arrow-icon {
        fill: white;
        filter: drop-shadow(0 0 2px rgba(0, 0, 0, 0));
    }

    .bestseller-link-btn:hover {
        background-color: black;
        border-color: white;
    }

        .bestseller-link-btn:hover a {
            color: white;
        }

    .product-image-container {
        position: relative;
    }

    .sizes-info-container {
        position: absolute;
        bottom: 0;
        left: 0;
        right: 0;
        max-height: 135px;
        overflow: hidden;
        background-color: rgba(255, 255, 255, 0.9);
        transition: height 0.3s ease;
    }

    .sizes-grid {
        display: flex;
        justify-content: left;
        align-items: center;
        padding-top: 20px;
        padding-left: 10px;
    }

    .size-box {
        width: 40px;
        height: 40px;
        background-color: black;
        color: white;
        display: flex;
        justify-content: center;
        align-items: center;
        margin: 2px;
        font-size: 14px;
        font-weight: bold;
        transition: transform 0.3s ease;
        cursor: pointer;
    }

        .size-box:hover {
            background-color: white;
            border: 1px solid black;
            color: black;
        }

    .favorite-container {
        display: flex;
        justify-content: left;
        align-items: center;
        padding-left: 10px;
        margin-top: 10px;
    }

    .favorite-box {
        width: 50px;
        height: 40px;
        background-color: white;
        color: black;
        border: 1px solid black;
        display: flex;
        justify-content: center;
        align-items: center;
        margin: 2px;
        cursor: pointer;
        clear: both;
    }

    .favorite-icon {
        width: 20px;
        height: 20px;
    }
</style>
