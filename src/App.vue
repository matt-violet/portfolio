<template>
  <div id="app">
    <MenuBar class="components menu" @onMenuClick="onMenuClick" :currentPg="currentPg"/>
    <Home class="components home" v-if="home"/>
    <About v-if="about"/>
    <Portfolio v-if='portfolio'/>
    <Contact v-if='contact'/>
  </div>
</template>

<script>
import Home from './components/Home.vue'
import MenuBar from './components/MenuBar.vue'
import About from './components/About.vue'
import Portfolio from './components/Portfolio.vue'
import Contact from './components/Contact.vue'

export default {
  name: 'app',
  components: {
    MenuBar,
    Home,
    About,
    Portfolio,
    Contact
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
    background-color: gainsboro;
  }
  .components {
    width: 100%;
    z-index: 2;
    left: 50%;
    transform: translate(-50%);
    position: fixed;
  }
  .home {
    position: inline-block;
    margin-top: 120px;
  }
</style>
