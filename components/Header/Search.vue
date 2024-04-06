<script setup>
const searchInputRef = ref();
const searchInput = ref(false);

const toggleSearchInput = () => {
  searchInput.value = !searchInput.value;
  nextTick(() => searchInput.value && searchInputRef.value.focus());
};
</script>

<template>
  <div class="search">
    <img
      class="search_icon"
      src="/icons/search.svg"
      alt="Search"
      @click="toggleSearchInput"
    />
    <Transition>
      <input
        class="search_input"
        placeholder="Szukaj"
        ref="searchInputRef"
        v-show="searchInput"
      />
    </Transition>
  </div>
</template>

<style>
.search {
  height: 26px;
  position: relative;
}

.search_icon {
  cursor: pointer;
}

.search_input {
  position: absolute;
  right: 30px;
  top: -5px;
  height: 36px;
  width: 300px;
  padding: 0 10px;
  border: 1px solid #9a9a9a;
  font-family: "Bitter", sans-serif;
  font-size: 11px;
  transition: opacity 0.4s ease-in-out;
}
.search_input::placeholder {
  text-transform: uppercase;
}
.search_input:focus {
  outline: none;
  box-shadow: 0 0 3px 1px #68a8e0;
}

.v-enter-active,
.v-leave-active {
  transition: opacity 0.4s ease-in-out;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}

@media only screen and (max-width: 768px) {
  .search {
    position: static;
  }

  .search_input {
    top: 100%;
    right: 0;
    width: 100%;
  }
}
</style>
