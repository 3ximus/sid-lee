<script setup>
import { RouterLink } from "vue-router";
import { onBeforeMount } from "vue";
import IntroView from "./IntroView.vue";
import PassionComponent from "../components/PassionComponent.vue";

const MOVEMENT_ATTENUATION = 0.25;

const fullWidth = window.innerWidth;
const fullHeight = window.innerHeight;

const xOffset = (val) =>
  document.body.style.setProperty(
    "--x-offset",
    `${(val * MOVEMENT_ATTENUATION).toFixed(0)}px`,
  );

const OnMouseMove = (event) => {
  xOffset(-event.clientX + fullWidth / 2);
};

// Link event
document.body.addEventListener("mousemove", OnMouseMove);

// Lifecycle Events
onBeforeMount(() => {
  xOffset(0);
});
</script>

<template>
  <main>
    <div class="background">
      <div class="left">
        <div class="inner">
          <img class="sign" src="/resume.webp" alt="" />
        </div>
      </div>
      <div class="right">
        <div class="inner">
          <img class="sign" src="/passion.webp" alt="" />
        </div>
      </div>
    </div>

    <h1 class="tag resume">RESUME</h1>
    <h1 class="tag passions">PASSIONS</h1>

    <PassionComponent />

    <footer>
      <h1 class="footer">Move mouse to either side</h1>
    </footer>

    <div class="vignette"></div>
    <IntroView></IntroView>
  </main>
</template>

<style scoped>
.vignette {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  box-shadow: 0 0 300px rgba(0, 0, 0, 0.9) inset;
  pointer-events: none;
}
.title {
  position: absolute;
  top: 0;
  width: 100vw;
  text-align: center;
  font-size: 2rem;
}
.footer {
  position: absolute;
  bottom: 0;
  left: 50px;
  font-size: 1.5rem;
}

.background {
  width: calc(100vw + 800px);
  height: 100vh;
  position: relative;
  left: calc(-400px + var(--x-offset));
}
.left,
.right {
  width: 55%;
  height: 100%;
  top: 0;
  transform: skewX(-10deg);
  overflow: hidden;
}
.left {
  position: relative;
  left: -5%;
}
.right {
  position: absolute;
  right: -5%;
}
.left .inner,
.right .inner {
  width: 100%;
  height: 100%;
  background-size: cover;
  background-repeat: no-repeat;
  transform: skewX(10deg);
}
.left .inner {
  background-color: #bad4aa;
  margin-left: 12%;
}
.right .inner {
  background-color: #260d04;
  margin-left: -12%;
}
.sign {
  padding-left: 5%;
  width: 55%;
  position: relative;
  top: 13%;
}
.right .inner .sign {
  left: -16%;
}
.left .inner .sign {
  left: 60%;
}

.tag {
  top: 45%;
  position: fixed;
  font-size: 80px;
  font-family: kenyan-coffee;
}
.tag.passions {
  right: -70px;
  color: #bad4aa;
  transform: rotate(90deg);
}
.tag.resume {
  left: -50px;
  color: #260d04;
  transform: rotate(-90deg);
}
</style>
