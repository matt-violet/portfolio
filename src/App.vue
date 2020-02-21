<template>
  <div id="app">
    <MenuBar class="menu" @onMenuClick="onMenuClick" :currentPg="currentPg"/>
    <div class="components">
      <Home class='home'/>
      <!-- <Blurb class='blurb'/> -->
      <About/>
      <Skills/>
      <Projects/>
      <Contact/>
    </div> 
  </div>
</template>

<script>
import Home from './components/Home.vue'
import MenuBar from './components/MenuBar.vue'
// import Blurb from './components/Blurb.vue'
import About from './components/About.vue'
import Skills from './components/Skills.vue'
import Projects from './components/Projects.vue'
import Contact from './components/Contact.vue'

export default {
  name: 'app',
  components: {
    MenuBar,
    Home,
    // Blurb,
    About,
    Skills,
    Projects,
    Contact,
  },
  data() {
    return {
      currentPg: '',
      home: true,
      about: false,
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
    background: rgb(236, 236, 236);
    height: 100%;
    margin: 0;
    font-family: 'IBM Plex Sans', 'Montserrat', sans-serif;
  }
</style>
