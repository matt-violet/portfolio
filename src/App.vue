<template>
  <div id="app">
    <MenuBar class="components menu" @menuClick="menuClick"/>
    <Home class="components about" v-if="home"/>
    <About v-if="about"/>
    <div v-if="home" class="background img1"/>
  </div>
</template>

<script>
import Home from './components/Home.vue'
import MenuBar from './components/MenuBar.vue'
import About from './components/About.vue'

export default {
  name: 'app',
  components: {
    MenuBar,
    Home,
    About
  },
  data() {
    return {
      home: true,
      about: false,
      portfolio: false,
      contact: false
    }
  },
  methods: {
    menuClick(option) {
      this.home = false;
      this.about = false;
      this.portfolio = false;
      this.contact = false;
      this[option] = true;
    }
  }
}
</script>

<style>
  body, html {
    height: 100%;
    width: 100%;
    margin: 0;
    font-family: Arial, Helvetica, sans-serif;
  }
  .components {
    width: 100%;
    z-index: 2;
    left: 50%;
    transform: translate(-50%);
    position: fixed;
  }
  .about {
    position: inline-block;
    margin-top: 120px;
  }
  .background {
    z-index: 1;
    height: 1000px;
    background-position: center top;
    background-repeat: no-repeat;
    background-size: cover;
  }
  .img1 {
    background-image: url('./images/oakland-sunset.jpg');
    height: 900px;
    opacity: .75;
  }
</style>
