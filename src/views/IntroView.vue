<script setup>
import { ref } from "vue";
let showIntro = ref(true);

setTimeout(() => {
  showIntro.value = false;
}, 2000);
</script>

<template>
  <transition name="fade">
    <div v-if="showIntro">
      <h2>HELLO</h2>
      <h1>SID LEE LAND</h1>
      <div class="backdrop"></div>
    </div>
  </transition>
</template>

<style scoped>
div {
  position: absolute;
  top: 0;
  left: 0;
  width: 100vw;
  display: flex;
  align-items: center;
  justify-content:;
  height: 100vh;
  flex-direction: column;
  color: #260d04;
}
img {
  z-index: 2;
}
h2 {
  z-index: 2;
  transform: scaleY(0.18) translateY(10vh);
  font-size: 41vw;
  font-family: kenyan-coffee;
  margin: 0;
  height: 100px;
}
h1 {
  z-index: 2;
  margin: 0;
  transform: scaleX(0.4) translateY(-20vh);
  font-size: 45vw;
  white-space: nowrap;
  font-family: kenyan-coffee;
}
.backdrop {
  background-color: #bad4aa;
  animation: mymove 5s 1 forwards;
}

@keyframes mymove {
  from {
    opacity: 100%;
  }
  to {
    opacity: 50%;
  }
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 1s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>
