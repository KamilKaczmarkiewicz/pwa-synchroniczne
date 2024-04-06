<script setup>
import { ref } from 'vue';
const drawer = ref(false);
</script>

<template>
  <div class="side-panel">
    <img
      class="side-panel-icon"
      src="/icons/shopping_bag.svg"
      alt="Cart"
      @click="drawer = true"
    />

    <Transition
      @before-enter="beforeEnter"
      @after-leave="afterLeave"
    >
      <div class="side-panel-wrapper" v-show="drawer">
        <div class="side-panel-overlay" @click="drawer = false"></div>
        <div class="side-panel-drawer">
          <div class="side-panel-content">
            <div class="side-panel-msg">Jest tu pusto!</div>
          </div>
          <div class="side-panel-close" @click="drawer = false"></div>
        </div>
      </div>
    </Transition>
  </div>
</template>

<style>
.side-panel {
  height: 26px;
}

.side-panel-icon {
  cursor: pointer;
  padding-left: 26px;
  border-left: 1px solid #d8d8d8;
}

.side-panel-wrapper {
  position: fixed;
  z-index: 999;
}

.side-panel-overlay {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background-color: rgba(0, 0, 0, 0.7);
  transition: opacity 0.4s ease-in-out;
}

.side-panel-drawer {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  width: 355px;
  background-color: white;
  transition: transform 0.4s ease-in-out;
}

.side-panel-content {
  height: 100%;
  width: 100%;
  padding: 30px 20px 30px 30px;
}

.side-panel-msg {
  display: flex;
  justify-content: center;
  font-family: "Bitter", sans-serif;
  font-size: 14px;
  line-height: 20px;
  font-weight: 700;
  padding: 30px 0;
  color: black;
}

.side-panel-close {
  position: absolute;
  height: 40px;
  width: 40px;
  top: 16px;
  right: 8px;
  cursor: pointer;
}
.side-panel-close:before,
.side-panel-close:after {
  content: "";
  position: absolute;
  left: 50%;
  top: 50%;
  height: 18px;
  width: 1px;
  background-color: #111111;
}
.side-panel-close:before {
  transform: translate(-50%, -50%) rotate(45deg);
}
.side-panel-close:after {
  transform: translate(-50%, -50%) rotate(-45deg);
}

.v-enter-active .side-panel-overlay,
.v-leave-active .side-panel-overlay {
  transition: opacity 0.4s ease-in-out;
}

.v-enter-from .side-panel-overlay,
.v-leave-to .side-panel-overlay {
  opacity: 0;
}

.v-enter-active .side-panel-drawer,
.v-leave-active .side-panel-drawer {
  transition: transform 0.4s ease-in-out;
}

.v-enter-from .side-panel-drawer,
.v-leave-to .side-panel-drawer {
  transform: translateX(300%);
}

@media only screen and (max-width: 1024px) {
  .side-panel-icon {
    padding-left: 0;
    border-left: 0;
  }
}
</style>
