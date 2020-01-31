<template>
  <div class="projects-wrapper">
    <div v-for="project in portfolio" v-bind:key="project.id" class="project">
      <div class="img-div">
        <img :src="project.image" class='img'/>
      </div>
      <h2>{{ project.title }}</h2>
        <p>{{ project.description }}</p>
        <p>{{ project.stack }}</p>
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
          stack: 'HTML, CSS, Javascript, React',
          image: require('../images/connect-four.png')
        },
        MyBolus: {
          id: 2,
          title: 'My Bolus',
          description: 'Insulin dose calculator for diabetics',
          stack: 'HTML, CSS, Javascript, React, Express, MongoDB',
          image: require('../images/bolus-calculator.png')
        },
        OpenRestaurant: {
          id: 3,
          title: 'Open Restaurant',
          description: 'Photos module for restaurant app',
          stack: ' HTML, CSS, Javascript, React, Styled-Components, Express, MongoDB, Faker, Jest, Enzyme',
          image: require('../images/open-restaurant.png')
        },
        SocialInn: {
          id: 4,
          title: 'Social Inn',
          description: 'Scaled back end of housing app',
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
  .projects-wrapper {
    margin-top: 150px;
    margin-left: 100px;
    position: absolute;
  }
  .project {
    border: 1px solid;
    width: 300px;
    height: 300px;
    background-color: white; opacity: .70;
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
  p {
    font-size: 14px;
    line-height: normal;
    color: black;
  }
</style>