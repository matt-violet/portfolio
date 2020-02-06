<template>
  <div id="app">
    <MenuBar class="menu" @onMenuClick="onMenuClick" :currentPg="currentPg"/>
    <div class="components">
      <Home class="home" v-if="home"/>
      <About v-if="about"/>
      <Portfolio v-if="portfolio" @viewProjectDetails="viewProjectDetails"/>
      <Contact v-if="contact"/>
      <ProjectDetails v-if="projectDetails" :project="project" @viewProjectDetails="viewProjectDetails"/>
      
      <div v-if="portfolio" class="bg-div-portfolio">
        <img src="./images/laptop5.jpg" class="bg-img-portfolio"/>
        <!-- <div class="white-overlay"/> -->
      </div>
      
      <div v-if="contact" class="contact-bg-div">
        <img src="./images/radio.jpg" class="contact-bg-img"/>
          <!-- <div class="white-overlay"/> -->
      </div>
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
    },
    viewProjectDetails(project) {
      this.project = project;
      this.projectDetails = !this.projectDetails;
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
  .menu {
    width: 100%;
    position: relative;
    display: block;
    z-index: 1;
  }
  .components {
    width: 100%;
    /* height: 100%; */
    /* position: fixed; */
  }
    /* -------------------------- HOME PAGE -------------------------- */
  .home {
    position: fixed;
    min-width: 100%;
    min-height: 100%;
  }
  /* -------------------------- ABOUT PAGE -------------------------- */
  .about-bg-div {
    position: absolute;
    overflow: hidden;
    z-index: -1;
    width: 100%;
  }
  .about-bg-img1 {
    opacity: .75;
    width: 100%;
    min-height: (100% - 70px);
  }
  .about-bg-img2 {
    width: 100%;
    height: 420px;
    opacity: .6;
    position: relative;
    background-color: lightgray;
  }
  /* -------------------------- PORTFOLIO PAGE -------------------------- */
  .bg-div-portfolio {
    position: fixed;
    width: 100%;
    height: 100%;
    z-index: -1;
    overflow: hidden;
    flex-direction: column;
    justify-content: center;
    display: flex;
  }
  .bg-img-portfolio {
    position: fixed;
    right: 0;
    min-height: 100%;
    min-width: 100%;

  }
  .white-overlay {
    margin: 0 auto 0 auto;
    height: 100%;
    width: 1000px;
    background-color: white; 
    opacity: .5;
    border: 1px solid gray;
    animation-duration: .75s;
    animation-name: slideDown;
  }
  /* -------------------------- CONTACT PAGE -------------------------- */
  .contact-bg-div {
    width: 100%;
    height: 100%;
    position: fixed;
    z-index: -1;
  }
  .contact-bg-img {
    position: fixed;
    min-width: 100%;
    min-height: 100%;
    /* opacity: .5; */
    z-index: -1;
  }
  /* ----------------------------------------------------------------- */
  @keyframes slideDown {
    from { transform: translateY(-1000px); }
    to { transform: translateY(0px); }
  }
</style>
