<template>
  <div class="outer-wrapper">
    
    <table cellpadding="0" cellspacing="0">
      <tr cellpadding="0" cellspacing="0">
        <td>Skills:</td>
        <td class="icon">
          <svg viewBox="0 0 128 128">
            <path fill="#000000" d="M19.569 27l8.087 89.919 36.289 9.682 36.39-9.499 8.096-90.102h-88.862zm72.041 20.471l-.507 5.834-.223 2.695h-42.569l1.017 12h40.54l-.271 2.231-2.615 28.909-.192 1.69-22.79 6.134v-.005l-.027.012-22.777-5.916-1.546-17.055h11.168l.791 8.46 12.385 3.139.006-.234v.012l12.412-2.649 1.296-13.728h-38.555l-2.734-30.836-.267-3.164h55.724000000000004l-.266 2.471zM27.956 1.627h5.622v5.556h5.144v-5.556h5.623v16.822h-5.623v-5.633h-5.143v5.633h-5.623v-16.822zM51.738 7.206h-4.95v-5.579h15.525v5.579h-4.952v11.243h-5.623v-11.243zM64.777 1.627h5.862l3.607 5.911 3.603-5.911h5.865v16.822h-5.601v-8.338l-3.867 5.981h-.098l-3.87-5.981v8.338h-5.502v-16.822zM86.513 1.627h5.624v11.262h7.907v5.561h-13.531v-16.823z"></path>
          </svg>
        </td>
        <td class="icon">
          <svg viewBox="0 0 128 128">
            <path fill="#000000" d="M19.67 26l8.069 90.493 36.206 10.05 36.307-10.063 8.078-90.48h-88.66zm69.21 50.488l-2.35 21.892.009 1.875-22.539 6.295v.001l-.018.015-22.719-6.225-1.537-17.341h11.141l.79 8.766 12.347 3.295-.004.015v-.032l12.394-3.495 1.308-14.549h-25.907000000000004l-.222-2.355-.506-5.647-.265-2.998h27.886000000000003l1.014-11h-42.473l-.223-2.589-.506-6.03-.265-3.381h55.597l-.267 3.334-2.685 30.154"></path><path fill="#000000" d="M89 14.374l-7.149-8.374h7.149v-5h-16v4.363l8.39 7.637h-8.39v5h16zM70 14.374l-6.807-8.374h6.807v-5h-15v4.363l7.733 7.637h-7.733v5h15zM52 13h-8v-7h8v-5h-14v17h14z"></path>
          </svg>
        </td>
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
    margin: 5px 0px 5px 0px;
    color: black;
  }
  p {
    font-size: 14px;
    line-height: normal;
    color: black;
    margin: 0;
  }
  tr {
    height: 30px;
  }
  td {
    border-spacing: 0;
    text-align: center;
    height: 30px;
    width: 30px;
  }
  table {
    margin-left: auto;
    margin-right: auto;
    border-collapse: collapse;
    left: 0;
    right: 0;
  }
  .icon {
    background-color: white;
    border-radius: 50%;
    padding: 10px;
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
    overflow: hidden;
    border: 1px solid black;
  }
  .img {
    width: 100%;
    height: auto;
  }
</style>