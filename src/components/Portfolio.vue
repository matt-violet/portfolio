<template>
  <div class="outer-wrapper">
    
    <table cellpadding="0" cellspacing="0">
      <tr cellpadding="0" cellspacing="0">
        <td>Skills:</td>
        <td><i class="icon devicon-html5-plain-wordmark"></i></td>
        <td><i class="icon devicon-css3-plain"></i></td>
        <td><i class="icon devicon-javascript-plain"></i></td>
        <td><i class="icon devicon-react-original-wordmark"></i></td>
        <td><i class="icon devicon-vuejs-plain-wordmark"></i></td>
        <td><i class="icon devicon-jquery-plain-wordmark"></i></td>
        <td><i class="icon devicon-nodejs-plain-wordmark"></i></td>
        <td><i class="icon devicon-express-original"></i></td>
        <td><i class="icon devicon-mongodb-plain-wordmark"></i></td>
        <td><i class="icon devicon-postgresql-plain-wordmark"></i></td>
        <td><i class="icon devicon-mysql-plain-wordmark"></i></td>
        <td><i class="icon devicon-webpack-plain-wordmark"></i></td>
        <td><i class="icon devicon-amazonwebservices-plain-wordmark"></i></td>
      </tr>
    </table>

    <div class="projects-wrapper">
      <div
        v-for="project in portfolio" 
        v-on:click="$emit('viewProjectDetails', project)"
        v-bind:key="project.id"
        class="project"
      >
        <div class="img-div">
          <img :src="project.image" class='img'/>
        </div>
        <h2>{{ project.title }}</h2>
          <p>{{ project.description }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Portfolio',
  data() {
    return {
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
          image: require('../images/bolus-calculator.png')
        },
        OpenRestaurant: {
          id: 3,
          title: 'Open Restaurant',
          description: 'Photos module for restaurant app',
          details: 'Built responsive image gallery with modal view showing photo details, flagging options, and intuitive navigation. Designed database schema to optimize loading speeds by hosting images in AWS S3 buckets',
          stack: ' HTML, CSS, Javascript, React, Styled-Components, Express, MongoDB, Faker, Jest, Enzyme',
          image: require('../images/open-restaurant.png')
        },
        SocialInn: {
          id: 4,
          title: 'Social Inn',
          description: 'Scaled back end of housing app',
          details: 'Scaled the back end of a room reviews app to handle 10 million records and 100 requests per second. Benchmarked performance of a SQL vs. NoSQL database with 10M records to determine optimal database. Deployed app on AWS and stress tested server to identify performance bottlenecks',
          stack: 'PostgreSQL, Cassandra, Express, Amazon Web Services, k6, New Relic',
          image: require('../images/social-inn.png')
        }
      }
    }
  }  
}
</script>

<style scoped>
  h2 {
    margin: 10px 0px 10px 0px;
    color: black;
  }
  p {
    font-size: 14px;
    line-height: normal;
    color: black;
  }
  td {
    border-spacing: 0;
    padding: 0;
    margin: 0;
    text-align: center;
    height: 70px;
    /* border: 1px solid black; */
  }
  table {
    margin-left: auto;
    margin-right: auto;
    border-collapse: collapse;
    left: 0;
    right: 0;
    width: 900px;
    height: 70px;
  }
  .icon {
    height: 100%;
    width: 100%;
    border: .5px solid;
    background-color: white;
    border-radius: 50%;
    padding: 10px;
    left: 0;
    right: 0;
  }
  .outer-wrapper {
    margin-top: 125px;
    left: 0;
    right: 0;
    width: 100%;
    height: 100%;
    position: absolute;
  }
  .projects-wrapper {
    margin-top: 25px;
    position: absolute;
    margin-left: auto;
    margin-right: auto;
    left: 0;
    right: 0;
  }
  .project {
    border: 1px solid;
    width: 300px;
    background-color: white; opacity: .85;
    margin: 20px;
    padding: 10px;
    float: left;
    display: inline-block;
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
    border: 1px solid black;
  }
  .img {
    width: 100%;
    height: 100%;
  }
</style>