<template>
  <div id="app">
    <MenuBar class="menu" @onMenuClick="onMenuClick" :currentPg="currentPg"/>
    <div class="components">
      <About v-if="about"/>
      <Projects
        v-if="projects"
        :viewProjectDetails="showProjectDetails"
        :project="featuredProject"
        :softwareProjects="softwareProjects"
        :designProjects="designProjects"
        :videoProjects="videoProjects"
      />
      <ProjectDetails
        data-aos="fade-in"
        v-if="projectDetails"
        :project="featuredProject"
        @viewProjectDetails="showProjectDetails"
      />
      <Contact v-if="contact"/>
    </div> 
  </div>
</template>

<script>
import MenuBar from './components/MenuBar.vue'
import About from './components/About.vue'
import Projects from './components/Projects.vue'
import Contact from './components/Contact.vue'
import ProjectDetails from './components/ProjectDetails.vue'
import { softwareProjects, designProjects, videoProjects } from '../project-data';

export default {
  name: 'app',
  components: {
    MenuBar,
    About,
    Projects,
    ProjectDetails,
    Contact,
  },
  data() {
    return {
      currentPg: '',
      about: false,
      projects: true,
      contact: false,
      projectDetails: false,
      featuredProject: {},
      softwareProjects: softwareProjects,
      designProjects: designProjects,
      videoProjects: videoProjects
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
    },
    showProjectDetails(project) {
      this.featuredProject = project;
      this.projectDetails = !this.projectDetails;
    },
  }
}
</script>

<style>
  body, html {
    min-height: 100%;
    min-width: 600px;
    margin: 0;
    font-family: 'IBM Plex Sans', 'Montserrat', sans-serif;
  }
  a {
    color: blue;
    font-weight: 400;
  }
</style>
