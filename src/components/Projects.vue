<template>
  <div class="projects-component" id="portfolio">
    <h1 class='software-projects-header'>
      SOFTWARE PROJECTS
    </h1>
    <div class="projects-wrapper">
      <CarouselSoftware class='software-carousel' :project="project" @viewProjectDetails="viewProjectDetails"/>
      <div class='other-div'>
        <h1 class="other-projects-header">
          OTHER PROJECTS
        </h1>
        <CarouselDesign class='inline-carousel' :project="project" @viewProjectDetails="viewProjectDetails"/>
        <CarouselVideo class='inline-carousel'/>
      </div>
    </div>
  </div>
</template>

<script>
import CarouselSoftware from './CarouselSoftware.vue'
import CarouselDesign from './CarouselDesign.vue'
import CarouselVideo from './CarouselVideo.vue'

export default {
  name: 'Portfolio',
  components: {
    CarouselSoftware,
    CarouselDesign,
    CarouselVideo,
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
  .projects-component {
    width: 100%;
    padding-top: 40px;
    padding-bottom: 100px;
    background: rgb(236, 236, 236);
  }
  .software-projects-header {
    padding: 40px 0 5px 0;
    text-align: center;
    margin: 0 auto 40px auto;
    width: 400px;
    border-bottom: solid 1px;
  }
  .projects-header {
    margin: 0 auto;
  }
  .projects-wrapper {
    width: 100%;
    margin: 0 auto;
    left: 0;
    right: 0;
  }
  .projects-wrapper {
    margin-bottom: 50px;
    display: inline-block;
  }
  .projects-header {
    margin: auto;
  }
  .other-projects-header {
    width: 330px;
    border-bottom: 1px solid;
    margin: 80px auto;
    padding: 0 auto 5px auto;
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
    cursor: pointer;
  }
  .design-imgs {
    border: 1px solid gray;
    border-radius: 5px;
    width: 100%;
  }
  .software-carousel {
    margin: 40px auto;
  }
  .inline-carousel {
    display: inline-block;
    margin: 0 80px;
  }
  .other-div {
    margin: 0 auto;
    text-align: center;
  }
</style>