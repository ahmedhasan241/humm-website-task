<template>
  <div class="subscribe">
    <slot />
  </div>
</template>

<script setup></script>

<style scoped>
.subscribe {
  background: #000;
  min-height: 100vh;
  display: flex;
  -webkit-box-align: center;

  align-items: center;
  -webkit-box-pack: center;
  justify-content: center;
  position: relative;
  z-index: 2;
  overflow: hidden;
}
.subscribe::after {
  content: "";
  position: absolute;
  top: 2vw;
  right: 2vw;
  left: 2vw;
  bottom: 2vw;
  background-image: url(../assets/images/cover.png);
  background-repeat: no-repeat;
  background-size: cover;
  z-index: -1;
}

@media (max-width: 768px) {
  .subscribe {
    background-color: white;
  }
  .subscribe::after {
    display: none;
  }
}
</style>
