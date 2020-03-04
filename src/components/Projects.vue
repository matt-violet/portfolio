<template>
  <div class="projects-wrapper">
    <div class="projects-banner">
      <div class="left animatedParent">
        <div class="left-side-text animated slideInDown">
          <h1 class='projects-banner-text'>
            Here's what I've been up to.
          </h1>
          <p class='projects-banner-text-2'>
            Check out my latest projects in software, design, and video.
          </p>
        </div>
      </div>
      <div class="right animatedParent">
        <img src="../images/matt-oak-blank.png" class="right-side-img animated slideInUp">
      </div>
    </div>
    <div class="projects-component">
      <h1 class='project-page-header'>Projects</h1>
      <div class="header-container">
        <div class='expand software-expand' v-on:click='onShowSoftware'>
          <img src='../images/icon-software.png' class='project-icon'>
          <h1 class='project-section-header'>
            Software
          </h1>
          <img src='../images/up-arrow.png' class='project-arrow' v-if='!showSoftware'>
          <img src='../images/down-arrow.png' class='project-arrow' v-if='showSoftware'>
        </div>
        <div class="software-projects" v-show='showSoftware'>
          <SoftwareProjects
            :softwareProjects="softwareProjects"
            @viewProjectDetails="showProjectDetails"
          />
        </div>
          <div class='expand design-expand' v-on:click='onShowDesign'>
            <img src='../images/icon-design.png' class='project-icon'>
            <h1 class="project-section-header">
              Design
            </h1>
            <img src='../images/up-arrow.png' class='project-arrow' v-if='!showDesign'>
            <img src='../images/down-arrow.png' class='project-arrow' v-if='showDesign'>
          </div>
          <div v-show='showDesign' class='design-carousel-div'>
            <CarouselDesign
              class='design-carousel'
              :designProjects="designProjects"
              @viewProjectDetails="showProjectDetails"
            />
          </div>
          <div :class="showVideo ? 'expand video-expand' : 'expand video-expanded'" v-on:click='onShowVideo'>
            <img src='../images/icon-video.png' class='project-icon'>
            <h1 class="project-section-header">
              Video
            </h1>
            <img src='../images/up-arrow.png' class='project-arrow' v-if='!showVideo'>
            <img src='../images/down-arrow.png' class='project-arrow' v-if='showVideo'>
          </div>
          <CarouselVideo
            v-show='showVideo'
            class='video-carousel'
            :videoProjects="videoProjects"
          />
          <ProjectDetails
            v-if="projectDetails"
            :project="featuredProject"
            @viewProjectDetails="showProjectDetails"
          />

      </div>
    </div>
  </div>
</template>

<script>
import CarouselDesign from './CarouselDesign.vue'
import CarouselVideo from './CarouselVideo.vue'
import SoftwareProjects from './SoftwareProjects.vue'
import ProjectDetails from './ProjectDetails.vue'

export default {
  name: 'Projects',
  components: {
    CarouselDesign,
    CarouselVideo,
    SoftwareProjects,
    ProjectDetails,
  },
  methods: {
    onShowVideo() {
      this.showVideo = !this.showVideo
    },
    onShowDesign() {
      this.showDesign = !this.showDesign
    },
    onShowSoftware() {
      this.showSoftware = !this.showSoftware
    },
    showProjectDetails(project) {
      this.featuredProject = project;
      this.projectDetails = !this.projectDetails;
    }
  },
  data() {
    return {
      featuredProject: {},
      projectDetails: false,
      showDesign: false,
      showVideo: false,
      showSoftware: false,
      softwareProjects: [
        {
          id: 1,
          title: 'Connect Four',
          description: 'Single Page Connect Four Game',
          details: 'Developed game in which two players alternately place pieces into a 7x7 board trying to place 4 adjacent pieces. Implemented animations and dynamically rendering board, game status, and rematch button',
          stack: 'HTML, CSS, Javascript, React',
          github: 'https://github.com/matt-violet/connect4',
          image: require('../images/connect-four.png'),
          video: 'https://www.youtube.com/embed/AM0sI6ZqEQw'
        },
        {
          id: 2,
          title: 'My Bolus',
          description: 'Insulin dose calculator for diabetics',
          details: 'Developed an app to simulate modern insulin pump dosage algorithms based on user’s meal choice, current blood glucose (bg) level, insulin-to-carb ratio, bg correction factor, future exercise plans, and other factors',
          stack: 'HTML, CSS, Javascript, React, Express, MongoDB',
          github: 'https://github.com/matt-violet/My-Bolus',
          image: require('../images/vial.jpg'),
          video: 'https://www.youtube.com/embed/OsGm4uK7SEs'
        },
        {
          id: 3,
          title: 'Open Restaurant',
          description: 'Photos module for restaurant app',
          details: 'Built responsive image gallery with modal view showing photo details, flagging options, and intuitive navigation. Designed database schema to optimize loading speeds by hosting images in AWS S3 buckets',
          stack: ' HTML, CSS (grid, media query), Javascript, React, Styled-Components, Express, MongoDB, Faker, Jest, Enzyme',
          github: 'https://github.com/krummurk/photos-module',
          image: require('../images/restaurant.jpg'),
          video: 'https://www.youtube.com/embed/LZBo0UIRxvI'
        },
        {
          id: 4,
          title: 'Social Inn',
          description: 'Scaled back end of housing app',
          details: 'Scaled the back end of a room reviews app to handle 10 million records and 100 requests per second. Benchmarked performance of a SQL vs. NoSQL database with 10M records to determine optimal database. Deployed app on AWS and stress tested server to identify performance bottlenecks',
          stack: 'PostgreSQL, Cassandra, Express, Amazon Web Services, k6, New Relic',
          github: 'https://github.com/social-inn/Reviews',
          image: require('../images/bed.jpg')
        }
      ],
      designProjects: [
        {
          image: require('../images/Symposium2019.jpg'),
          description: 'Event Flyer, 2019',
          design: true
        },
        {
          image: require('../images/GA2017.png'),
          description: 'Recruitment Flyer, 2018',
          design: true
        },
        {
          image: require('../images/SKSM-banner.jpg'),
          description: '8-foot Retractable Banner, 2017',
          design: true
        },
        {
          image: require('../images/GA2016-flyer.png'),
          description: 'Ad in UU World Magazine, 2016',
          design: true
        },
        // {
        //   image: require('../images/GA2017-flyer.png'),
        //   description: 'Ad in UU World Magazine, 2017',
        //   design: true
        // },
        {
          image: require('../images/GA2018-flyer.png'),
          description: 'Ad in UU World Magazine, 2018',
          design: true
        },
        {
          image: require('../images/HLTW.png'),
          description: 'Designed layout of book "Hunter Leads the Way", 2017',
          design: true
        },
        {
          image: require('../images/SEAsia.png'),
          description: 'Graphic for Personal Project, 2015',
          design: true
        },
        {
          image: require('../images/matt-oak.png'),
          description: 'Graphic for Personal Project, 2019',
          design: true
        },
      ],
      videoProjects: [
        {
          title: 'Starr King Threshold Ceremony, 2017',
          description: 'The Starr King community gathers to welcome new students to the school.',
          url: 'https://www.youtube.com/embed/Boi3G8wiEAY'
        },
        {
          title: 'A Mindful Walk: Immersion Course, 2018',
          description: 'Experience Transylvania\'s hills and river valleys, cultural sites, and more in this unforgettable immersion couse.',
          url: 'https://www.youtube.com/embed/6eKqxxVSlKQ'
        },
        {
          title: 'Soaring Sunday, 2015',
          description: 'Discover the art of soaring as we take flight over Byron, CA in this meditative-like weekend recap.',
          url: "https://player.vimeo.com/video/118749275"
        }
      ],
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
  .projects-wrapper {
    background-image: linear-gradient(to right, rgba(253,193,104), rgba(251,128,128));
    height: 100%;
    margin-bottom: 100px;
  }
  .projects-component {
    width: 1000px;
    padding: 60px 0;
    margin: auto;
    border: 1px solid;
    border-radius: 20px;
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
    background-image: linear-gradient(to right, rgba(253,193,104), rgba(251,128,128));
  }
  .left {
    width: 55%;
    height: 400px;
    display: inline-block;
    text-align: left;
    position: relative;
  }
  .right {
    width: 45%;
    height: 400px;
    position: relative;
    display: inline-block;
    overflow: hidden;
  }
  .right-side-img {
    height: 95%;
    margin: 0 auto 0 20px;
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
    font-size: 50px;
    margin: 0;
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
    width: 100px;
    text-align: center;
    font-size: 25px;
  }
  .project-section-header {
    margin: 10px 20px;
    font-size: 25px;
    display: inline-block;
  }
  .header-container {
    padding: 0 80px;
    width: 700px;
    margin: auto;
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
  .software-carousel {
    margin: 40px auto;
  }
  .video-carousel {
    background: hsl(16, 100%, 66%, .5);
    padding: 40px 0;
    border-bottom-left-radius: 10px;
    border-bottom-right-radius: 10px;
  }
  .software-projects {
    height: 600px;
    padding: 40px 0;
    background: hsl(39, 77%, 83%, .5);
  }
  .design-carousel-div {
    transition: max-height 0.2s ease-out;
    margin: auto;
    background: hsl(28, 87%, 67%, .5);
    padding: 40px 0;
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
  }
  .software-expand {
    background: hsl(39, 77%, 83%, .5);
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
  }
  .design-expand {
    background: hsl(28, 87%, 67%, .5);
  }
  .video-expand {
    background: hsl(16, 100%, 66%, .5);
  }
  .video-expanded {
    background: hsl(16, 100%, 66%, .5);
    border-bottom-left-radius: 10px;
    border-bottom-right-radius: 10px;
  }
</style>