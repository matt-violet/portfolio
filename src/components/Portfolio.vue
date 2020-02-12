<template>
  <div class="portfolio-component" id="portfolio">
    <div class="outer-wrapper">
      <a class="resume-link" target="_blank" href="https://docs.google.com/document/d/1QNbQGA8xYZ_rY8bJt6Y7lT9yVWhXIu7WmLypJb6UrZU/edit?usp=sharing">
        View Resume
      </a>
      <h1 class="projects-header">Software Projects</h1>

      <div class="projects-wrapper">
        <div
          v-for="(project, i) in softwarePortfolio" 
          v-on:click="$emit('viewProjectDetails', project)"
          v-bind:key="i"
          class="project-div"
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
        <div v-for="(project, i) in designPortfolio"
          v-on:click="$emit('viewProjectDetails', project)"
          v-bind:key="i"
          class="design-project-div"
        >
          <img :src="project.image" class="design-imgs"/>
          <p>{{ project.description }}</p>
        </div>
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
          title: 'Open Restaurant',
          description: 'Responsive photo gallery for a restaurant review app',
          details: 'Welcome to the photos module for Open Restaurant! The photos module presents the user with an image gallery for a given restaurant. The photos module enables full-screen modal viewing of each gallery photo with responsive sizing, associated photo details, and intuitive navigation of gallery photos. The "restaurant_id" is determined by the 1-8 digit number included at the end of the url. When the gallery page component mounts, the restuarant_id is sent in a GET request to an Express server that queries a MongoDB database for image urls of photos stored on Amazon Web Services.',
          stack: ' HTML, CSS, Javascript, React, Styled-Components, Express, MongoDB, Faker, Jest, Enzyme',
          image: require('../images/open-restaurant.png'),
          github: 'https://github.com/krummurk/photos-module'
        },
        SocialInn: {
          title: 'Social Inn',
          description: 'Scaled the back end of a rental accommodations app',
          details: 'Social-Inn is an online marketplace for users to book or offer lodging. This module displays all reviews associated with a particular room. I scaled this module\'s back end to handle 10 million records and 100 requests per second. I benchmarked performance of a SQL vs. NoSQL database with 10M records to determine optimal database. I deployed app on AWS and stress tested server to identify performance bottlenecks.',
          stack: 'PostgreSQL, Cassandra, Express, Amazon Web Services, k6, New Relic',
          image: require('../images/couch.jpg'),
          github: 'https://github.com/social-inn/Reviews'
        },
        connect4: {
          title: 'Connect Four',
          description: 'Game in which two players drop discs into slots and connect four to win',
          details: 'This app is modeled after the popular "Connect Four" game published by Milton Bradley in 1974 in which two players alternate dropping pieces into a 7x7 board trying to occupy 4 adjacent spaces. The app utilizes CSS animations and a dynamically rendering board (based on a two dimensional array), game status, head-to-head score, and rematch button.',
          stack: 'HTML, CSS, Javascript, React',
          image: require('../images/connect-four.png'),
          github: 'https://github.com/matt-violet/connect4'
        },
        MyBolus: {
          title: 'My Bolus',
          description: 'Calculating the proper dose of medication can be tough for diabetics. My Bolus makes it easy!',
          details: 'This app simulates modern insulin pump technology by implementing a complex algorithm allowing users to calculate their bolus based on meal choice, current blood glucose (bg) level, insulin-to-carb ratio, bg correction factor, future exercise plans, and other factors.',
          stack: 'HTML, CSS, Javascript, React, Express, MongoDB',
          image: require('../images/math.jpg'),
          github: 'https://github.com/matt-violet/My-Bolus'
        }
      },
      designPortfolio: {
        ga2016: {
          image: require('../images/GA2016-flyer.png'),
          description: 'Ad in UU World Magazine, 2016',
          design: true
        },
        ga2017: {
          image: require('../images/GA2017-flyer.png'),
          description: 'Ad in UU World Magazine, 2017',
          design: true
        },
        ga2018: {
          image: require('../images/GA2018-flyer.png'),
          description: 'Ad in UU World Magazine, 2018',
          design: true
        },
        ga2019: {
          image: require('../images/Symposium2019.jpg'),
          description: 'Event Flyer, 2019',
          design: true
        },
        symposium2019: {
          image: require('../images/GA2017.png'),
          description: 'Recruitment Flyer, 2018',
          design: true
        },
        SEAsia: {
          image: require('../images/SEAsia.png'),
          description: 'Personal Side Project, 2015',
          design: true
        },
        sksmBanner: {
          image: require('../images/SKSM-banner.jpg'),
          description: '8-foot Retractable Banner, 2017',
          design: true
        },
      }
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
  p {
    font-size: 12px;
    line-height: normal;
    color: black;
    margin: 0;
  }
  .portfolio-component {
    padding-top: 150px;
  }
  .outer-wrapper {
    width: 850px;
    margin: 0 auto;
    left: 0;
    right: 0;
  }
  .projects-wrapper {
    margin-bottom: 50px;
    display: inline-block;
  }
  .projects-header {
    text-align: left;
    font-size: 50px;
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
    transform: scale(1.03);
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
    transform: scale(1.03);
    cursor: pointer;
  }
  .design-imgs {
    border: 1px solid gray;
    border-radius: 5px;
    width: 100%;
  }
  .resume-link {
    display: inline-block;
  }
</style>