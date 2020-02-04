<template>
  <div class="outer-wrapper">
    <a class="resume-link" target="_blank" href="https://docs.google.com/document/d/1QNbQGA8xYZ_rY8bJt6Y7lT9yVWhXIu7WmLypJb6UrZU/edit?usp=sharing">
      View Resume
    </a>
    <h1 class="projects-header">Software Projects</h1>

    <div class="projects-wrapper">
      <div
        v-for="project in softwarePortfolio" 
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

    <div class="design-wrapper">
      <h1 class="design-header">Graphic Design</h1>
      <div v-for="project in designPortfolio"
        v-on:click="$emit('viewProjectDetails', project)"
        v-bind:key="project.id"
        class="design-project-div"
      >
        <img :src="project.image" class="design-imgs"/>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Portfolio',
  data() {
    return {
      softwarePortfolio: {
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
        },
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
        }
      },
      designPortfolio: {
        ga2016: {
          id: 1,
          image: require('../images/GA2016-flyer.png'),
          type: 'design'
        },
        ga2017: {
          id: 2,
          image: require('../images/GA2017-flyer.png'),
          type: 'design'
        },
        ga2018: {
          id: 3,
          image: require('../images/GA2018-flyer.png'),
          type: 'design'
        },
        ga2019: {
          id: 4,
          image: require('../images/Symposium2019.jpg'),
          type: 'design'
        },
        symposium2019: {
          id: 5,
          image: require('../images/GA2017.png'),
          type: 'design'
        },
        sksmBanner: {
          id: 6,
          image: require('../images/SKSM-banner.jpg'),
          type: 'design'
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
  .outer-wrapper {
    margin-top: 125px;
    width: 850px;
    margin-left: auto;
    margin-right: auto;
    left: 0;
    right: 0;
    position: absolute;
  }
  .projects-wrapper {
    margin-bottom: 50px;
    display: inline-block;
  }
  .projects-header {
    text-align: left;
    font-size: 50px;
    animation-duration: .75s;
    animation-name: slideDown;
  }
  .design-header {
    text-align: left;
    font-size: 50px;
  }
  .project {
    border: 1px solid;
    width: 225px;
    background-color: lavender;
    margin: 15px;
    padding: 10px;
    display: inline-block;
    animation-duration: .75s;
    animation-name: slideLeft;
  }
  .project:hover {
    transform: scale(1.03);
    cursor: pointer;
  }
  .img-div {
    height: 110px;
    overflow: hidden;
    border: 1px solid black;
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
    display: inline-block;
    overflow: hidden;
    padding: 10px;
    background-color: lavender;
    border: 1px solid;
    vertical-align: top;
  }
  .design-project-div:hover {
    transform: scale(1.03);
    cursor: pointer;
  }
  .design-imgs {
    border: 1px solid;
    width: 200px;
  }
  .resume-link {
    display: inline-block;
    margin-top: 50px;
    animation-duration: .75s;
    animation-name: slideRight;
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