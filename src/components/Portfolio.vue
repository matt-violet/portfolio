<template>
  <div class="portfolio-component" id="portfolio">
    <div class="portfolio-wrapper">
      <a class="resume-link" target="_blank" href="https://docs.google.com/document/d/1QNbQGA8xYZ_rY8bJt6Y7lT9yVWhXIu7WmLypJb6UrZU/edit?usp=sharing">
        View Resume
      </a>
      <h1 class="projects-header" v-on:click="toggleSoftwareProjects">
        Software Projects
      </h1>
      <CarouselSoftware :project="project" @viewProjectDetails="viewProjectDetails"/>
      <h1 class="design-header">Graphic Design</h1>
      <CarouselDesign :project="project" @viewProjectDetails="viewProjectDetails"/>
    </div>
  </div>
</template>

<script>
import CarouselSoftware from './CarouselSoftware.vue'
import CarouselDesign from './CarouselDesign.vue'

export default {
  name: 'Portfolio',
  components: {
    CarouselSoftware,
    CarouselDesign,
  },
  props: {
    viewProjectDetails: {type: Function},
    project: {type: Object},
  },
  methods: {
    toggleSoftwareProjects() {
      // alert('click')
      if (this.$data.showSoftwareCarousel) {
        this.$data.showSoftwareCarousel = false;
      } else {
        this.$data.showSoftwareCarousel = true;
      }
    }
  },
  data() {
    return {
      showSoftwareCarousel: false
    }
  }
}
</script>

<style scoped>
  h2 {
    margin: 5px 0px 5px 0px;
    color: black;
    font-size: 18px;
  }
  p {
    font-size: 12px;
    line-height: normal;
    color: black;
    margin: 0;
  }
  .portfolio-component {
    padding-top: 100px;
    padding-bottom: 100px;
    background: lightsalmon;
  }
  .portfolio-wrapper {
    width: 850px;
    margin: 0 auto;
    left: 0;
    right: 0;
  }
  .projects-wrapper {
    margin-bottom: 50px;
    display: inline-block;
  }
  .projects-header {
    text-align: left;
    font-size: 50px;
  }
  .projects-header:hover {
    cursor: pointer;
  }
  .design-header {
    text-align: left;
    font-size: 50px;
  }
  .project-div {
    border: 1px solid gray;
    border-radius: 5px;
    width: 235px;
    background-color: white;
    margin: 15px;
    padding: 7px;
    display: inline-block;
  }
  .project-div:hover {
    transform: scale(1.03);
    cursor: pointer;
  }
  .img-div {
    height: 110px;
    overflow: hidden;
    border: 1px solid gray;
    border-radius: 5px;
  }
  .img {
    width: 100%;
    height: auto;
  }
  .design-wrapper {
    width: 850px;
    margin-left: auto;
    margin-right: auto;
  }
  .design-project-div {
    margin: 15px;
    width: 235px;
    display: inline-block;
    overflow: hidden;
    padding: 7px;
    background-color: white;
    border: 1px solid gray;
    border-radius: 5px;
    vertical-align: top;
  }
  .design-project-div:hover {
    transform: scale(1.03);
    cursor: pointer;
  }
  .design-imgs {
    border: 1px solid gray;
    border-radius: 5px;
    width: 100%;
  }
  .resume-link {
    display: inline-block;
  }
</style>