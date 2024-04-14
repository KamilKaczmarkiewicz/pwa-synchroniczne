<script setup>
const navigation = [
  {
    label: "Sklep",
    link: "https://clickfashion.pl/sklep",
    children: [
      {
        label: "Kolekcja",
        link: "https://clickfashion.pl/sklep/kolekcja",
      },
      {
        label: "Sukienki | Kombinezony",
        link: "https://clickfashion.pl/sklep/sukienki-kombinezony",
      },
      {
        label: "Bluzki | Koszule",
        link: "https://clickfashion.pl/sklep/bluzki-koszule",
      },
      {
        label: "Marynarki",
        link: "https://clickfashion.pl/sklep/marynarki",
      },
      {
        label: "Płaszcze | Kurtki",
        link: "https://clickfashion.pl/sklep/plaszcze-i-kurtki.html",
      },
      {
        label: "Spodnie",
        link: "https://clickfashion.pl/sklep/spodnie",
      },
      {
        label: "Spódnice",
        link: "https://clickfashion.pl/sklep/spodnice-223.html",
      },
      {
        label: "Swetry",
        link: "https://clickfashion.pl/sklep/swetry",
      },
      {
        label: "Golfy",
        link: "https://clickfashion.pl/sklep/golfy.html",
      },
    ],
  },
  {
    label: "Kolekcja zimowa",
    link: "https://clickfashion.pl/jesienzima.html",
  },
  {
    label: "Stylizacje wieczorowe",
    link: "https://clickfashion.pl/stylizacje-wieczorowe.html",
  },
  {
    label: "Stylizacje codzienne",
    link:"stylizacje-codzienne",
  },
  {
    label: "Kolekcja świąteczna",
    link: "https://clickfashion.pl/kolekcja-swiateczna.html",
  },
  {
    label: "Wyprzedaż",
    link: "https://clickfashion.pl/sale-205.html",
  },
  {
    label: "Nowości",
    link: "https://clickfashion.pl/nowosci.html",
  },
];

const isNavChildrenVisible = ref(false);

const toggleNavChildrenVisible = () => {
  isNavChildrenVisible.value = !isNavChildrenVisible.value;
};
</script>

<template>
  <nav>
    <div class="user-account">
      <span class="material-symbols-outlined"> person </span>
      <a href="https://clickfashion.pl/customer/account/" target="_blank"
        >MOJE KONTO</a
      >
    </div>
    <ul>
      <li v-for="(item, index) of navigation" class="nav-item">
        <span class="nav-item-content">
          <a :href="item.link" target="_blank" class="desktop"
            >{{ item.label }}
          </a>
          <span v-if="index === 0" class="material-symbols-outlined desktop">
            expand_more
          </span>
          <a
            v-if="index === 0"
            @click="toggleNavChildrenVisible()"
            class="mobile"
            :class="index === 0 ? 'shop' : ''"
            >{{ item.label }}
          </a>
          <a v-if="index !== 0" :href="item.link" target="_blank" class="mobile"
            >{{ item.label }}
          </a>
          <span
            v-if="index === 0"
            @click="toggleNavChildrenVisible()"
            class="material-symbols-outlined mobile"
          >
            expand_more
          </span>
        </span>
        <div
          v-if="index === 0 && isNavChildrenVisible"
          class="nav-item-children mobile"
        >
          <ul>
            <li>
              <a href="https://clickfashion.pl/sklep" target="_blank"
                >Wszystkie</a
              >
            </li>
            <li v-for="item of navigation[0].children">
              <a :href="item.link" target="_blank">{{ item.label }}</a>
            </li>
          </ul>
        </div>
      </li>
      <div class="nav-item-children desktop">
        <ul>
          <li v-for="item of navigation[0].children">
            <a :href="item.link" target="_blank">{{ item.label }}</a>
          </li>
        </ul>
      </div>
    </ul>
  </nav>
</template>

<style scoped lang="scss">
nav {
  padding: 10px 40px;
  width: 100%;
  max-width: 1600px;

  @media screen and (max-width: 1700px) {
    max-width: 1140px;
  }

  @media screen and (min-width: 992px) {
    .user-account {
      display: none;
    }
  }

  @media screen and (max-width: 991px) {
    position: fixed;
    top: 120px;
    left: 0;
    height: 100%;
    padding: 20px 0px;
    z-index: 9;
    overflow-y: scroll;
    background-color: #fff;

    .user-account {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 23px;
      font-size: 12px;
      font-weight: bold;
      letter-spacing: 1px;
      margin-bottom: 36px;
    }
  }
}
ul {
  list-style: none;
  display: flex;

  @media screen and (max-width: 991px) {
    flex-direction: column;
  }
}
.nav-item {
  position: relative;
}

a {
  color: black;
  text-decoration: none;
  text-transform: uppercase;
}

.nav-item-content {
  display: flex;
  width: 100%;
  align-items: center;
  padding: 12px 20px;

  @media screen and (min-width: 992px) {
    .mobile {
      display: none;
    }
  }

  @media screen and (max-width: 991px) {
    justify-content: center;
    font-size: 30px;
    padding: 23px 75px;

    .desktop {
      display: none;
    }

    .mobile {
      display: inline-block;

      &.shop {
        margin-left: auto;
        cursor: pointer;
      }
    }

    span.mobile {
      display: inline;
      margin-left: auto;
      cursor: pointer;
    }
  }

  a {
    display: inline-block;
    position: relative;

    &::after {
      content: "";
      background: #000;
      height: 2px;
      width: 0;
      transition: 0.4s width ease-in-out;
      position: absolute;
      bottom: -13px;
      left: 0;
    }
  }

  &:hover {
    a::after {
      width: 100%;
    }
  }
}

.nav-item:first-child:hover ~ .nav-item-children.desktop,
.nav-item-children.desktop:hover {
  @media screen and (min-width: 992px) {
    display: block;
  }
}

.nav-item-children {
  position: absolute;
  display: none;
  left: 0;
  right: 0;
  top: 220px;
  background-color: #fff;

  &.mobile {
    position: relative;
    display: block;
    top: unset;
    left: unset;
    right: unset;
    background-color: #f5f5f5;

    @media screen and (min-width: 992px) {
      display: none;
    }

    ul li {
      width: 100%;
      padding: 14px 0;
      font-weight: normal;
      text-align: center;
    }
  }

  ul {
    flex-direction: column;
    margin: 0 auto;
    padding: 10px 40px;
    width: 100%;
    max-width: 1600px;

    @media screen and (max-width: 1700px) {
      max-width: 1140px;
    }

    li {
      width: max-content;
      padding: 6px 8px;
      font-family: sans-serif;
      font-size: 14px;
      font-weight: bold;
      text-transform: uppercase;
    }
  }
}
</style>
