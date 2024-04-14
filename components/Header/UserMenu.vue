<script setup>
import { ref } from "vue";

const isNavVisible = defineProps(['modelValue'])
const toggleNavVisible = defineEmits(['update:modelValue'])

const isSearchInputVisible = ref(false);

const searchInputRef = ref(null);

const toogleSearchInputVisible = () => {
  isSearchInputVisible.value = !isSearchInputVisible.value;
};

const handleSearchIconClick = () => {
  toogleSearchInputVisible();
  setTimeout(() => {
    searchInputRef.value?.focus();
  }, 150);
};

const searchProduct = () => {
  const searchValue = searchInputRef.value.value;
  
  window.open(`https://clickfashion.pl/catalogsearch/result/?q=${searchValue}`, '_blank');
};

const handleMenuIconClick = () => {
  toggleNavVisible('update:modelValue', !isNavVisible.modelValue)
}
</script>

<template>
  <div class="user-menu">
    <input
      v-if="isSearchInputVisible"
      v-on:keyup.enter="searchProduct()"
      class="search-input"
      ref="searchInputRef"
      type="text"
      placeholder="SZUKAJ W SKLEPIE..."
    />
    <span @click="handleSearchIconClick()" class="material-symbols-outlined search-icon">
      search
    </span>
    <a href="https://clickfashion.pl/customer/account/" target="_blank"
      ><span class="material-symbols-outlined"> person </span></a
    >
    <a href="https://clickfashion.pl/wishlist/" target="_blank">
      <span class="material-symbols-outlined"> favorite </span>
    </a>
    <div class="separation"></div>
    <a href="https://clickfashion.pl/checkout/cart/" target="_blank">
      <span class="material-symbols-outlined"> shopping_bag </span>
    </a>
    <span @click="handleMenuIconClick()" class="material-symbols-outlined menu-icon">
      {{ isNavVisible.modelValue ? 'close' : 'menu' }}
    </span>
  </div>
</template>

<style scoped lang="scss">
.user-menu {
  display: flex;
  align-items: center;
  gap: 20px;

  .menu-icon{
    cursor: pointer;
    display: none;
  }

  @media screen and (max-width: 991px) {
    .separation, a:nth-of-type(1), a:nth-of-type(2){
      display: none;
    }

    .menu-icon {
      display: inline;
    }
  }

  .search-icon {
    cursor: pointer;
  }


}

.search-input {
  all: unset;
  padding: 10px;
  width: 300px;
  height: 36px;
  color: #676767;
  font-size: 14px;
  box-sizing: border-box;
  border: 1px solid #676767;

  &:focus {
    border-width: 1px;
    box-shadow: 0 0 3px 1px #68a8e0;
  }
}

.separation {
  display: block;
  width: 2px;
  height: 24px;
  background-color: rgb(216, 216, 216);
}

a {
  color: black;
  text-decoration: none;
}
</style>
