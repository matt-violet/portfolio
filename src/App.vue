<template>
  <div id="app">
    <div class="bg"/>
    <MenuBar class="menu" @onMenuClick="onMenuClick" :currentPg="currentPg"/>
    <div class="components">
      <Home class='home'/>
      <About class='about'/>
      <Portfolio class='portfolio' :project="project" @viewProjectDetails="viewProjectDetails"/>
      <ProjectDetails v-if="projectDetails" :project="project" @viewProjectDetails="viewProjectDetails"/>
      <Contact class='contact'/>
    </div> 
  </div>
</template>

<script>
import Home from './components/Home.vue'
import MenuBar from './components/MenuBar.vue'
import About from './components/About.vue'
import Portfolio from './components/Portfolio.vue'
import Contact from './components/Contact.vue'
import ProjectDetails from './components/ProjectDetails.vue'

export default {
  name: 'app',
  components: {
    MenuBar,
    Home,
    About,
    Portfolio,
    Contact,
    ProjectDetails
  },
  data() {
    return {
      currentPg: '',
      home: true,
      about: false,
      portfolio: false,
      contact: false,
      projectDetails: false,
      project: {},
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
    viewProjectDetails(project) {
      alert('clicked')
      this.project = project;
      this.projectDetails = !this.projectDetails;
    }
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
    position: fixed;
  }
  .menu {
    width: 100%;
    position: fixed;
    z-index: 1;
    animation-duration: .75s;
    animation-name: slideDown;
  }
  .components {
    position: absolute;
    width: 100%;
    height: 100%;
    padding-bottom: 150px;
  }
  .home {
    padding-top: 60px;
  }
</style>
