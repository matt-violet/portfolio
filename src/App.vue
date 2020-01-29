<template>
  <div id="app">
    <MenuBar class="components"/>
    <About class="components"/>
    <div class="background img1"></div>
    <div class="background img2"></div>
  </div>
</template>

<script>
import About from './components/About.vue'
import MenuBar from './components/MenuBar.vue'

export default {
  name: 'app',
  components: {
    MenuBar,
    About
  }
}
</script>

<style>
  body, html {
    height: 100%;
    margin: 0;
    font-family: Arial, Helvetica, sans-serif;
  }
  .components {
      z-index: 2;
      left: 50%;
      transform: translate(-50%);
      position: fixed;
  }
  .background {
    z-index: 1;
    height: 900px;
    background-position: center top;
    background-repeat: no-repeat;
    background-size: cover;
  }
  .img1 {
    /* background-image: url('./images/oakland-sunset.jpg'); */
    background-image: url('./images/oakland-sunset.jpg');
  }
  .img2 {
    background-color: black;
  }
</style>
