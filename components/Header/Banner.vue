<script setup>
const deliveryBanner = ref(true);
</script>

<template>
  <div class="promo-banner" v-if="deliveryBanner">
    <p class="promo-text">
      <b>Zamów przed godziną 12:00, a zamówienie otrzymasz jutro!</b>
    </p>
    <button
      class="promo-close"
      @click="deliveryBanner = !deliveryBanner"
      aria-label="Zamknij baner"
    >
    </button>
  </div>
</template>

<style>
.promo-banner {
  display: grid;
  place-items: center;
  background-color: red;
  height: 36px;
  padding: 0 36px 0 12px;
  position: relative;
}

.promo-text {
  display: inline-flex;
  align-items: center;
  font-family: "Montserrat", sans-serif;
  font-size: 15px;
  font-weight: bold;
  letter-spacing: 0.8px;
  text-transform: uppercase;
  color: white;
}
.promo-text:before {
  content: "";
  background: url("/icons/local_shipping.svg") no-repeat center center;
  height: 16px;
  min-width: 16px;
  background-size: 16px;
  margin-right: 12px;
}

.promo-close {
  all: unset;
  position: absolute;
  right: 12px;
  top: 50%;
  transform: translateY(-50%);
  border: 2px solid white;
  border-radius: 50%;
  height: 18px;
  width: 18px;
  cursor: pointer;
  background-color: red;
}
.promo-close:before,
.promo-close:after {
  content: "";
  position: absolute;
  left: 50%;
  top: 50%;
  height: 8px;
  width: 1px;
  background-color: white;
}
.promo-close:before {
  transform: translate(-50%, -50%) rotate(45deg);
}
.promo-close:after {
  transform: translate(-50%, -50%) rotate(-45deg);
}
</style>
