<template>
  <div class="outer-wrapper">
    <div
      v-for="project in portfolio" 
      v-on:click='showProjectDetails(project)'
      v-bind:key="project.id"
      class="project"
    >
      <div class="img-div">
        <img :src="project.image" class='img'/>
      </div>
      <h2>{{ project.title }}</h2>
      <p>{{ project.description }}</p>
    </div>
    <ProjectDetails v-if="projectDetails" :project="featuredProject" @viewProjectDetails="showProjectDetails"/>
  </div>
</template>
<script>
import ProjectDetails from './ProjectDetails.vue'
export default {
  name: 'SoftwareProjects',
  props: {
    viewProjectDetails: { type: Function },
    project: { type: Object },
  },
  components: {
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
      portfolio: {
        connect4: {
          id: 1,
          title: 'Connect Four',
          description: 'Single Page Connect Four Game',
          details: 'Developed game in which two players alternately place pieces into a 7x7 board trying to place 4 adjacent pieces. Implemented animations and dynamically rendering board, game status, head-to-head score, and rematch button',
          stack: 'HTML, CSS, Javascript, React',
          image: require('../images/connect-four.png')
        },
        MyBolus: {
          id: 2,
          title: 'My Bolus',
          description: 'Insulin dose calculator for diabetics',
          details: 'Developed an app to simulate modern insulin pump dosage algorithms based on user’s meal choice, current blood glucose (bg) level, insulin-to-carb ratio, bg correction factor, future exercise plans, and other factors',
          stack: 'HTML, CSS, Javascript, React, Express, MongoDB',
          image: require('../images/vial.jpg')
        },
        OpenRestaurant: {
          id: 3,
          title: 'Open Restaurant',
          description: 'Photos module for restaurant app',
          details: 'Built responsive image gallery with modal view showing photo details, flagging options, and intuitive navigation. Designed database schema to optimize loading speeds by hosting images in AWS S3 buckets',
          stack: ' HTML, CSS, Javascript, React, Styled-Components, Express, MongoDB, Faker, Jest, Enzyme',
          image: require('../images/restaurant.jpg')
        },
        SocialInn: {
          id: 4,
          title: 'Social Inn',
          description: 'Scaled back end of housing app',
          details: 'Scaled the back end of a room reviews app to handle 10 million records and 100 requests per second. Benchmarked performance of a SQL vs. NoSQL database with 10M records to determine optimal database. Deployed app on AWS and stress tested server to identify performance bottlenecks',
          stack: 'PostgreSQL, Cassandra, Express, Amazon Web Services, k6, New Relic',
          image: require('../images/bed.jpg')
        }
      }
    }
  }  
}
</script>
<style scoped>
  h2 {
    margin: 5px 0px 5px 0px;
    color: black;
  }
  p {
    font-size: 14px;
    line-height: normal;
    color: black;
    margin: 0;
  }
  .header {
    margin-left: 20px;
  }
  .outer-wrapper {
    /* margin-left: 25px; */
    /* margin-right: 25px; */
    /* left: 0; */
    /* right: 0; */
    /* width: 100%; */
    /* height: 100%; */
    /* position: relative; */
  }
  .projects-header {
    animation-duration: .75s;
    animation-name: slideDown;
  }
  .project {
    /* border: 1px solid; */
    width: 300px;
    background-color: white;
    margin: 20px;
    padding: 10px;
    float: left;
    display: inline-block;
    animation-duration: .75s;
    animation-name: slideLeft;
  }
  .project:hover {
    -webkit-transform: scale(1.01);
    -ms-transform: scale(1.05);
    transform: scale(1.05);
    cursor: pointer;
  }
  .img-div {
    width: 100%;
    height: 150px;
    overflow: hidden;
    /* border: 1px solid gray; */
  }
  .img {
    width: 100%;
    height: auto;
  }
  @keyframes slideDown {
    from { transform: translateY(-500px); }
    to { transform: translateY(0px); }
  }
  @keyframes slideLeft {
    from { transform: translateX(1000px); }
    to { transform: translateX(0px); }
  }
</style>