<template>
  <div class="projects-component" id="portfolio">
    <h1 class='software-projects-header'>
      SOFTWARE PROJECTS
    </h1>
    <div class="projects-wrapper">
      <div class="software-projects">
        <SoftwareProjects
          :softwareProjects="softwareProjects"
          @viewProjectDetails="showProjectDetails"
        />
      </div>
      <div class='other-div'>
        <h1 class="other-projects-header">
          OTHER PROJECTS
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
          details: 'Developed game in which two players alternately place pieces into a 7x7 board trying to place 4 adjacent pieces. Implemented animations and dynamically rendering board, game status, head-to-head score, and rematch button',
          stack: 'HTML, CSS, Javascript, React',
          image: require('../images/connect-four.png')
        },
        {
          id: 2,
          title: 'My Bolus',
          description: 'Insulin dose calculator for diabetics',
          details: 'Developed an app to simulate modern insulin pump dosage algorithms based on user’s meal choice, current blood glucose (bg) level, insulin-to-carb ratio, bg correction factor, future exercise plans, and other factors',
          stack: 'HTML, CSS, Javascript, React, Express, MongoDB',
          image: require('../images/vial.jpg')
        },
        {
          id: 3,
          title: 'Open Restaurant',
          description: 'Photos module for restaurant app',
          details: 'Built responsive image gallery with modal view showing photo details, flagging options, and intuitive navigation. Designed database schema to optimize loading speeds by hosting images in AWS S3 buckets',
          stack: ' HTML, CSS, Javascript, React, Styled-Components, Express, MongoDB, Faker, Jest, Enzyme',
          image: require('../images/restaurant.jpg')
        },
        {
          id: 4,
          title: 'Social Inn',
          description: 'Scaled back end of housing app',
          details: 'Scaled the back end of a room reviews app to handle 10 million records and 100 requests per second. Benchmarked performance of a SQL vs. NoSQL database with 10M records to determine optimal database. Deployed app on AWS and stress tested server to identify performance bottlenecks',
          stack: 'PostgreSQL, Cassandra, Express, Amazon Web Services, k6, New Relic',
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
        {
          image: require('../images/GA2017-flyer.png'),
          description: 'Ad in UU World Magazine, 2017',
          design: true
        },
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
    padding-top: 40px;
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
  .software-projects {
    width: 800px;
    height: 500px;
    margin: 40px auto;
  }
  .inline-carousel {
    margin: 0 auto 80px auto;
  }
  .other-div {
    margin: 0 auto;
    text-align: center;
  }
</style>