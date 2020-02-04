<template>
  <div id="app">
    <MenuBar class="components menu" @onMenuClick="onMenuClick" :currentPg="currentPg"/>
    <Home class="components home" v-if="home"/>
    <About v-if="about"/>
    <Portfolio v-if="portfolio" @viewProjectDetails="viewProjectDetails"/>
    <Contact v-if="contact"/>
    <ProjectDetails v-if="projectDetails" :project="project" @viewProjectDetails="viewProjectDetails"/>
    <img v-if="home" src="./images/oakland-sunset.jpg" class="oakland-bg"/>
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
    /* background-color: lightgray; */
  }
  .oakland-bg {
    /* opacity: .85; */
    background-position: right top;
    position: fixed;
    z-index: -1;
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
