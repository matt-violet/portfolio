<template>
  <div id="app">
    <div class="bg"/>
    <MenuBar class="menu" @onMenuClick="onMenuClick" :currentPg="currentPg"/>
    <div class="components">
      <Home class='home'/>
      <Blurb class='blurb'/>
      <About/>
      <Projects/>
      <Contact class='contact'/>
    </div> 
  </div>
</template>

<script>
import Home from './components/Home.vue'
import MenuBar from './components/MenuBar.vue'
import Blurb from './components/Blurb.vue'
import About from './components/About.vue'
import Projects from './components/Projects.vue'
import Contact from './components/Contact.vue'
// import ProjectDetails from './components/ProjectDetails.vue'

export default {
  name: 'app',
  components: {
    MenuBar,
    Home,
    Blurb,
    About,
    Projects,
    Contact,
    // ProjectDetails
  },
  data() {
    return {
      currentPg: '',
      home: true,
      about: false,
      projects: false,
      contact: false,
      // projectDetails: false,
      // project: {},
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
  .bg {
    height: 100%;
    width: 100%;
  }
  .menu {
    width: 100%;
    position: fixed;
    z-index: 2;
    animation-duration: .75s;
    animation-name: slideDown;
  }
  .components {
    position: relative;
    width: 100%;
    height: 100%;
    overflow: hidden;
  }
  .home {
    width: 100%;
  }
</style>
