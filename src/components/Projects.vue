<template>
  <div class="projects-wrapper">
    <div class="projects-banner">
      <div class="left">
        <div class="left-side-text" data-aos="fade-right" data-aos-delay='300'>
          <h1 class='projects-banner-text'>
            Here's what I've been up to.
          </h1>
          <p class='projects-banner-text-2'>
            Check out my latest projects in software, design, and video.
          </p>
        </div>
      </div>
      <div class="right">
        <img src="../images/matt-oak-blank.png" class="right-side-img" data-aos="fade-up" data-aos-delay='300'>
      </div>
    </div>
    <div class="projects-component" data-aos="flip-up">
      <div data-aos="zoom-in" data-aos-delay='100'>
        <h1 class='project-page-header'>Projects</h1>
        <div class="header-container">
          <div :class="showSoftware ? 'expand software-expanded' : 'expand software-expand'" v-on:click='onShowSoftware'>
            <img src='../images/icon-software.png' class='project-icon'>
            <h1 class='project-section-header'>
              Software
            </h1>
            <img src='../images/up-arrow.png' class='project-arrow' v-if='!showSoftware'>
            <img src='../images/down-arrow.png' class='project-arrow' v-if='showSoftware'>
          </div>
          <transition
            name="expand"
            @enter="enter"
            @after-enter="afterEnter"
            @leave="leave"
          >
            <div class="software-projects" v-show='showSoftware'>
              <SoftwareProjects
                :softwareProjects="softwareProjects"
                @viewProjectDetails="viewProjDetails"
              />
            </div>
          </transition>
          <div :class="showDesign ? 'expand design-expanded' : 'expand design-expand'" v-on:click='onShowDesign'>
            <img src='../images/icon-design.png' class='project-icon'>
            <h1 class="project-section-header">
              Design
            </h1>
            <img src='../images/up-arrow.png' class='project-arrow' v-if='!showDesign'>
            <img src='../images/down-arrow.png' class='project-arrow' v-if='showDesign'>
          </div>
          <transition
            name="expand"
            @enter="enter"
            @after-enter="afterEnter"
            @leave="leave"
          >
            <div v-show='showDesign' class='design-carousel-div'>
              <CarouselDesign
                class='design-carousel'
                :designProjects="designProjects"
                @viewProjectDetails="viewProjectDetails"
              />
            </div>
          </transition>
          <div :class="showVideo ? 'expand video-expanded' : 'expand video-expand'" v-on:click='onShowVideo'>
            <img src='../images/icon-video.png' class='project-icon'>
            <h1 class="project-section-header">
              Video
            </h1>
            <img src='../images/up-arrow.png' class='project-arrow' v-if='!showVideo'>
            <img src='../images/down-arrow.png' class='project-arrow' v-if='showVideo'>
          </div>
          <transition
            name="expand"
            @enter="enter"
            @after-enter="afterEnter"
            @leave="leave"
          >
            <CarouselVideo
              v-show='showVideo'
              class='video-carousel'
              :videoProjects="videoProjects"
            />
          </transition>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import CarouselDesign from './CarouselDesign.vue'
import CarouselVideo from './CarouselVideo.vue'
import SoftwareProjects from './SoftwareProjects.vue'

export default {
  name: 'Projects',
  props: {
    viewProjectDetails: { type: Function},
    softwareProjects: {type: Array},
    designProjects: {type: Array},
    videoProjects: {type: Array},
    project: {type: Object},
  },
  components: {
    CarouselDesign,
    CarouselVideo,
    SoftwareProjects,
  },
  methods: {
    enter(element) {
      const width = getComputedStyle(element).width;
      element.style.width = width;
      element.style.position = 'absolute';
      element.style.visibility = 'hidden';
      element.style.height = 'auto';
      const height = getComputedStyle(element).height;
      element.style.width = null;
      element.style.position = null;
      element.style.visibility = null;
      element.style.height = 0;
      getComputedStyle(element).height;
      setTimeout(() => {
        element.style.height = height;
      });
    },
    afterEnter(element) {
      element.style.height = 'auto';
    },
    leave(element) {
      const height = getComputedStyle(element).height;      
      element.style.height = height;
      getComputedStyle(element).height;
      setTimeout(() => {
        element.style.height = 0;
      });
    },
    onShowVideo() {
      this.showVideo = !this.showVideo
    },
    onShowDesign() {
      this.showDesign = !this.showDesign
    },
    onShowSoftware() {
      this.showSoftware = !this.showSoftware
    },
    viewProjDetails(project) {
      this.viewProjectDetails(project)
    }
  },
  data() {
    return {
      showDesign: false,
      showVideo: false,
      showSoftware: false,
    }
  }
}
</script>

<style scoped>
  * {
    will-change: height;
    transform: translateZ(0);
    backface-visibility: hidden;
    perspective: 1000px;
  }
  .expand-enter-active, .expand-leave-active {
    transition: height 1s ease-in-out;
    overflow: hidden;
  }
  .expand-enter, .expand-leave-to {
    height: 0;
  }
  h2 {
    margin: 5px 0px 5px 0px;
    color: black;
    font-size: 18px;
  }
  .projects-wrapper {
    background: linear-gradient(to left, rgba(253,193,104), rgba(251,128,128));
    height: 100%;
    margin-bottom: 100px;
  }
  .projects-component {
    width: 70%;
    padding: 0 0 60px 0;
    margin: auto;
    background: white;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.4), 0 6px 20px 0 rgba(0, 0, 0, 0.4);
    position: relative;
    z-index: 1;
  }
  .projects-banner {
    padding-top: 52px;
    width: 100%;
    height: 400px;
    position: relative;
    background: linear-gradient(to left, rgba(253,193,104), rgba(251,128,128));
  }
  .left {
    width: 50%;
    height: 400px;
    display: inline-block;
    text-align: left;
    position: relative;
  }
  .right {
    width: 50%;
    height: 400px;
    position: relative;
    display: inline-block;
    overflow: hidden;
  }
  .right-side-img {
    height: 95%;
    margin: 0 auto 0 30px;
    position: absolute;
    bottom: 0;
    left: 0;
  }
  .left-side-text {
    width: 400px;
    height: 200px;
    position: absolute;
    top: 0;
    bottom: 0;
    right: 0;
    color: rgb(43, 43, 43);
    margin: auto 20px auto 0;
  }
  .projects-banner-text {
    font-size: 55px;
    margin: 0 15px 0 0;
  }
  .title {
    font-size: 26px;
    margin: 0;
  }
  .projects-banner-text-2 {
    font-size: 20px;
  }
  .projects-wrapper {
    width: 100%;
    padding-bottom: 100px;
    margin: 0 auto;
    left: 0;
    right: 0;
    display: inline-block;
  }
  .project-page-header {
    margin: 0 auto 40px auto;
    padding: 40px 0;
    text-align: center;
    font-size: 32px;
    background: linear-gradient(to right, rgba(253,193,104,.5), rgba(251,128,128,.5));
  }
  .project-section-header {
    margin: 10px 20px;
    padding: 3px 0;
    font-size: 22px;
    display: inline-block;
  }
  .header-container {
    padding: 20px 0 0 0;
    margin: auto 80px;
  }
  .software-carousel {
    margin: 40px auto;
  }
  .video-carousel {
    background: hsl(16, 100%, 66%, .5);
    padding: 40px 0;
  }
  .software-projects {
    height: 600px;
    padding: 40px 0;
    background: hsl(39, 77%, 83%, .5);
  }
  .design-carousel-div {
    margin: auto;
    background: linear-gradient(to bottom, hsl(28, 87%, 67%, .5));
    padding: 40px 0;
  }
  .design-carousel {
    width: 80%;
  }
  .project-arrow {
    width: 15px;
    border: 1px solid;
    border-radius: 50%;
    padding: 5px;
    float: right;
    margin: 13px 0;
  }
  .project-icon {
    width: 30px;
    vertical-align: middle;
    margin: 0 0 10px 10px;
  }
  .expand {
    padding: 0 20px;
  }
  .expand:hover {
    cursor: pointer;
    /* font-size: 34px; */
    /* color: white; */
    /* transform: scale(1.02); */
  }
  .software-expand {
    background: hsl(39, 77%, 83%, .5);
  }
  .software-expanded {
    background: hsl(39, 77%, 83%, .5);
  }
  .design-expand {
    background: hsl(28, 87%, 67%, .5);
    border-bottom: 0px;
  }
  .design-expanded {
    background: hsl(28, 87%, 67%, .5);
  }
  .video-expand {
    background: hsl(16, 100%, 66%, .5);
  }
  .video-expanded {
    background: hsl(16, 100%, 66%, .5);
  }
  @media (max-width: 1250px) {
    .right-side-img {
      height: 85%;
      margin-left: 0;
    }
    .projects-banner-text {
      margin: 20px 0 0 0px;
      font-size: 42px;
    }
    .projects-banner-text-2 {
      font-size: 16px;
    }
    .projects-banner, .left, .right {
      height: 300px;
    }
    .left {
      width: 60%;
    }
    .right {
      width: 40%;
    }
  }
</style>