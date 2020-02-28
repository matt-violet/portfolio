<template>
  <div id="app">
    <MenuBar class="menu" @onMenuClick="onMenuClick" :currentPg="currentPg"/>
    <div class="components">
      <Home v-if="about"/>
      <About v-if="about"/>
      <Skills v-if="about"/>
      <Projects v-if="projects"/>
      <Contact v-if="contact"/>
    </div> 
  </div>
</template>

<script>
import Home from './components/Home.vue'
import MenuBar from './components/MenuBar.vue'
import About from './components/About.vue'
import Skills from './components/Skills.vue'
import Projects from './components/Projects.vue'
import Contact from './components/Contact.vue'

export default {
  name: 'app',
  components: {
    MenuBar,
    Home,
    About,
    Skills,
    Projects,
    Contact,
  },
  data() {
    return {
      currentPg: '',
      // home: true,
      about: true,
      projects: false,
      contact: false,
    }
  },
  methods: {
    onMenuClick(option) {
      this.home = false;
      this.about = false;
      this.projects = false;
      this.contact = false;
      this[option] = true;
      this.currentPg = option;
      if (option === 'home') {
        window.scroll({
          top: 0, 
          left: 0, 
          behavior: 'smooth'
        });
      } else {
      document.getElementById(option).scrollIntoView({ behavior: 'smooth' })
      }
    },
  }
}
</script>

<style>
  body, html {
    height: 100%;
    margin: 0;
    font-family: 'IBM Plex Sans', 'Montserrat', sans-serif;
  }
  a {
    color: rgb(43, 43, 43);
  }
  .menu {
    background: rgb(43, 43, 43);;
    color: white;
  }
</style>
