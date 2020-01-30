<template>
  <div id="app">
    <MenuBar class="components menu" @onMenuClick="onMenuClick" :currentPg="currentPg"/>
    <Home class="components about" v-if="home"/>
    <About v-if="about"/>
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
      currentPg: '',
      home: true,
      about: false,
      portfolio: false,
      contact: false
    }
  },
  methods: {
    onMenuClick(option) {
      this.home = false;
      this.about = false;
      this.portfolio = false;
      this.contact = false;
      this[option] = true;
      this.currentPg = option;
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
</style>
