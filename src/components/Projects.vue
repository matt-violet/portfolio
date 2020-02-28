<template>
  <div class="projects-component" id="portfolio">
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
        <img src="../images/matt-oak-blank.png" class="right-side-img animated slideInRight">
      </div>

    </div>
    <h1 class='software-projects-header'>
      Software Projects
    </h1>
    <div class="software-projects">
      <SoftwareProjects
        :softwareProjects="softwareProjects"
        @viewProjectDetails="showProjectDetails"
      />
    </div>
    <div class='other-wrapper'>
      <div class='other-div'>
        <h1 class="other-projects-header">
          Design & Video Projects
        </h1>
        <CarouselDesign
          class='inline-carousel'
          :designProjects="designProjects"
          @viewProjectDetails="showProjectDetails"
        />
        <CarouselVideo
          class='inline-carousel'
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
    showProjectDetails(project) {
      this.featuredProject = project;
      this.projectDetails = !this.projectDetails;
    }
  },
  data() {
    return {
      featuredProject: {},
      projectDetails: false,
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
          description: 'Designed layout of book "Hunter Leads the Way", 2017'
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
          title: 'Soaring Sunday, 2015',
          description: 'Discover the art of soaring as we take flight over Byron, CA in this meditative-like weekend recap.',
          url: "https://player.vimeo.com/video/118749275"
        },
        {
          title: 'Starr King Threshold Ceremony, 2017',
          description: 'The Starr King community gathers to welcome new students to the school.',
          url: 'https://www.youtube.com/embed/Boi3G8wiEAY'
        },
        {
          title: 'A Mindful Walk: Immersion Course, 2018',
          description: 'Experience Transylvania\'s hills and river valleys, cultural sites, and more in this unforgettable immersion couse.',
          url: 'https://www.youtube.com/embed/6eKqxxVSlKQ'
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
  .projects-component {
    width: 100%;
    /* margin: 120px auto 0 auto; */
    position: absolute;
    padding-top: 52px;
  }
  .projects-banner {
    /* padding-top: 52px; */
    width: 100%;
    height: 400px;
    position: relative;
    /* background: linear-gradient(90deg, #00C9FF 0%, #92FE9D 100%); */
        background-image: linear-gradient(to right, #eea2a2 0%, #bbc1bf 19%, #57c6e1 42%, #b49fda 79%, #7ac5d8 100%);    

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
    z-index: 2;
    overflow: hidden;
  }
  .right-side-img {
    height: 95%;
    margin: 0 auto 0 20px;
    position: absolute;
    bottom: 0;
    left: 0;
    /* right: 0; */
    /* z-index: 1; */
    /* -webkit-filter: drop-shadow(-8px -4px 8px #222);
    filter: drop-shadow(-8px -4px 8px #222); */
  }
  .left-side-text {
    width: 400px;
    height: 200px;
    position: absolute;
    top: 0;
    bottom: 0;
    right: 0;
    /* left: 0; */
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
    font-size: 16px;
  }


  .software-projects-header {
    text-align: center;
    margin: 80px auto 0 auto;
    font-size: 25px;
  }
  .projects-header {
    margin: auto;
  }
  .projects-wrapper {
    width: 100%;
    margin: 0 auto;
    left: 0;
    right: 0;
    display: inline-block;
  }
  .other-wrapper {
    padding: 80px 0;
  }
  .other-projects-header {
    margin: 0px auto 80px auto;
    font-size: 25px;
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
  .design-imgs {
    border: 1px solid gray;
    border-radius: 5px;
    width: 100%;
  }
  .software-carousel {
    margin: 40px auto;
  }
  .software-projects {
    width: 680px;
    height: 600px;
    margin: 40px auto 0 auto;
  }
  .inline-carousel {
    margin: 0 auto 80px auto;
  }
  .other-div {
    text-align: center;
  }
</style>