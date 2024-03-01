<script setup>
import { RouterLink } from "vue-router";
</script>

<template>
  <main>
    <div class="background">
      <RouterLink to="/resume">
        <div class="left">
          <div class="inner">
            <img class="sign" src="/resume.webp" alt="" />
          </div>
        </div>
      </RouterLink>
      <RouterLink to="/passions">
        <div class="right">
          <div class="inner">
            <img class="sign" src="/passion.webp" alt="" />
          </div>
        </div>
      </RouterLink>
    </div>

    <header class="title">
      <h1>Hello Sid Lee!</h1>
    </header>

    <div class="vignette"></div>
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
  width: 100%;
  transform: translateY(-50%, 0%);
}

.background {
  width: 120vw;
  height: 100vh;
  position: relative;
  left: -10vw;
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
  width: 70vh;
  position: relative;
  top: 17%;
}
.right .inner .sign {
  left: -16%;
}
.left .inner .sign {
  left: 60%;
}
</style>
