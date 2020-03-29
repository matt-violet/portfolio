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
        <div class="section-header">
          <div data-aos="zoom-in">
            <img src='../images/icon-software.png' class='project-icon'>
            <h1 class='section-title'>Software Projects</h1>
          </div>
        </div>
        <div class="software-projects" data-aos="zoom-in" data-aos-offset='300'>
          <SoftwareProjects
            :softwareProjects="softwareProjects"
            @viewProjectDetails="viewProjDetails"
          />
        </div>
        <div class='section-header'>
          <div data-aos="zoom-in">
            <img src='../images/icon-design.png' class='project-icon'>
            <h1 class="section-title">Design Projects</h1>
          </div>
        </div>          
        <div class='design-carousel-div' data-aos="zoom-in" data-aos-offset='300'>
          <CarouselDesign
            class='design-carousel'
            :designProjects="designProjects"
            @viewProjectDetails="viewProjectDetails"
          />
        </div>
        <div class='section-header'>
          <div data-aos="zoom-in">
            <img src='../images/icon-video.png' class='project-icon'>
            <h1 class="section-title">Video Projects</h1>
          </div>
        </div>
        <CarouselVideo
          class='video-carousel'
          data-aos="zoom-in"
          data-aos-offset='300'
          :videoProjects="videoProjects"
        />
      </div>
      <div class='divider-line' data-aos='zoom-in'/>
      <div class="resume-div">
        <a class='resume-header' v-on:click='onShowResume'> {{ showResume ? 'Hide Resume' : 'Show Resume' }} </a>
        <transition
          name="expand"
          @enter="enter"
          @after-enter="afterEnter"
          @leave="leave"
        >
          <img class='resume-img' v-if='showResume' src='../images/resume.jpg'/>
        </transition>
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
    onShowResume() {
      this.showResume = !this.showResume
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
      showResume: false,
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
    border-radius: 10px;
    overflow: hidden;
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
    height: 85%;
    margin: 0 auto 0 30px;
    position: absolute;
    bottom: 0;
    left: 0;
  }
  .left-side-text {
    width: 370px;
    height: 200px;
    position: absolute;
    top: 0;
    bottom: 0;
    right: 0;
    color: rgb(43, 43, 43);
    margin: auto 20px auto 0;
  }
  .projects-banner-text {
    font-size: 48px;
    font-weight: 700;
    margin: 0 15px 0 0;
  }
  .title {
    font-size: 26px;
    margin: 0;
  }
  .projects-banner-text-2 {
    font-size: 20px;
    font-weight: 300;
  }
  .projects-wrapper {
    width: 100%;
    padding-bottom: 100px;
    margin: 0 auto;
    left: 0;
    right: 0;
    display: inline-block;
  }
  .section-header {
    padding: 80px 0;
    text-align: center;
    vertical-align: middle;
    background: linear-gradient(to right, rgba(253,193,104,.5), rgba(251,128,128,.5));
  }
  .section-title {
    font-size: 32px;
    font-weight: 700;
    text-align: center;
    margin: 0;
    transform: translateY(-3px);
    display: inline-block;
  }
  .project-icon {
    width: 30px;
    display: inline-block;
    margin-right: 16px;
  }
  .video-carousel {
    padding: 60px 0;
  }
  .software-projects {
    padding: 60px 0;
  }
  .design-carousel-div {
    margin: auto;
    padding: 60px;
  }
  .design-carousel {
    width: 80%;
  }
  .resume-div {
    text-align: center;
    margin: 40px 0;
  }
  .resume-header {
    font-size: 16px;
  }
  .resume-img {
    width: 80%;
    display: block;
    margin: 0 auto;
    border-radius: 10px;
  }
  .resume-header:hover {
    cursor: pointer;
  }
  .divider-line {
    border-top: 1px solid lightgray;
    width: 80%;
    margin: 40px auto;
  }
  @media (max-width: 1100px) {
    .projects-component {
      width: 100%;
      border-radius: 0;
    }
    .projects-wrapper {
      padding: 0;
    }
    .right-side-img {
      margin-left: 0;
    }
    .projects-banner-text {
      margin: 20px 0 0 0px;
      font-size: 38px;
      width: 300px;
    }
    .projects-banner-text-2 {
      font-size: 14px;
    }
    .projects-banner, .left, .right {
      height: 250px;
    }
    .left {
      width: 60%;
    }
    .right {
      width: 40%;
    }
  }
  @media (max-width: 750px) {
    .left-side-text {
      width: 300px;
    }
  }
</style>