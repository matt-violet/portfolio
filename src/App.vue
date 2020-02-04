<template>
  <div id="app">
    <MenuBar class="components menu" @onMenuClick="onMenuClick" :currentPg="currentPg"/>
    <Home class="components home" v-if="home"/>
    <About v-if="about"/>
    <Portfolio v-if="portfolio" @viewProjectDetails="viewProjectDetails"/>
    <Contact v-if="contact"/>
    <ProjectDetails v-if="projectDetails" :project="project" @viewProjectDetails="viewProjectDetails"/>
    <div v-if="home" class="bg-div-sunset">
      <img src="./images/oakland-sunset.jpg" class="bg-img-sunset"/>
    </div>
    <div v-if="about" class="bg-div-map">
      <img src="./images/oakland-map.png" class="bg-img-map"/>
    </div>
    <!-- <div v-if="portfolio" class="bg-div-code">
      <img src="./images/code.png" class="bg-img-code"/>
    </div> -->
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
  .bg-div-sunset {
    position: fixed;
    z-index: -1;
  }
  .bg-div-map {
    position: absolute;
    z-index: -1;
    height: 430px;
    border: 1px solid lightgray;
  }
  .bg-div-code {
    position: absolute;
    height: 350px;
  }
  .bg-img-sunset {
    /* position: relative; */
  }
  .bg-img-map {
    opacity: .4;
    height: 100%;
    top: 0;
    object-fit: cover;
  }
  .bg-img-code {
    z-index: -1;
    opacity: .2;
    position: fixed;
    min-width: 100%;
    min-height: 100%;
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
