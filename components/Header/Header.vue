<script setup>
import Nav from "~/components/Header/Nav.vue";
import UserMenu from "~/components/Header/UserMenu.vue";
import { ref } from "vue";

const isHeaderInfoVisible = ref(true);
const isNavVisible = ref(true)
const headerInfo =
  "PRODUKTY TWORZONE RĘCZNIE, WYSYŁKA MOŻE WYDŁUŻYĆ SIĘ DO 5 DNI";

const toogleHeaderInfoVisible = () => {
  isHeaderInfoVisible.value = !isHeaderInfoVisible.value;
};
</script>

<template>
  <header>
    <div v-if="isHeaderInfoVisible" class="header-info">
      <span class="material-symbols-outlined"> quick_reorder </span>
      <p>{{ headerInfo }}</p>
      <button @click="toogleHeaderInfoVisible()">
        <span class="material-symbols-outlined"> cancel </span>
      </button>
    </div>
    <div class="user-panel">
      <img src="~/assets/logo.png" alt="logo" />
      <UserMenu v-model="isNavVisible"/>
    </div>
    <Nav v-if="isNavVisible" />
  </header>
</template>

<style scoped lang="scss">
header {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  @media screen and (max-width: 991px) {
    position: sticky;
    z-index: 9;
  }
}

.header-info {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 36px;
  padding: 14px;
  color: white;
  font-family: sans-serif;
  font-weight: bold;
  font-size: 11px;
  letter-spacing: 1px;
  gap: 12px;
  background-color: black;

  span {
    margin-left: auto;
  }

  button {
    all: unset;
    margin-left: auto;
    cursor: pointer;
  }

  .material-symbols-outlined {
    font-size: 20px;
  }
}

.user-panel {
  display: flex;
  padding: 25px 40px;
  width: 100%;
  max-width: 1600px;
  justify-content: space-between;
  align-items: center;

  @media screen and (max-width: 1700px) {
    max-width: 1140px;
  }
}
</style>
