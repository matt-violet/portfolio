<template>
  <div class="software-carousel-component">
    <img class="arrow back" src="../images/left-arrow.png" v-on:click="handleBack">
    <div class="track-container">
      <div class='img-div'>
        <img class='img' :src="softwarePortfolio[currentSlide].image" v-on:click="$emit('viewProjectDetails', softwarePortfolio[currentSlide])"/>
      </div>
      <div class='software-text-div'>
        <h2>{{ softwarePortfolio[currentSlide].title }}</h2>
        <p>{{ softwarePortfolio[currentSlide].description }}</p>
      </div>
    </div>
    <img class="arrow next" src="../images/right-arrow.png" v-on:click="handleNext">
    <div class="carousel-nav">
      <button class="carousel-indicator" :class="currentSlide === 0 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(0)"/>
      <button class="carousel-indicator" :class="currentSlide === 1 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(1)"/>
      <button class="carousel-indicator" :class="currentSlide === 2 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(2)"/>
      <button class="carousel-indicator" :class="currentSlide === 3 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(3)"/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CarouselSoftware',
  props: {
    viewProjectDetails: { type: Function },
    project: { type: Object },
  },
  methods: {
    handleNext: function() {
      if (this.currentSlide < 3) {
        this.currentSlide++
      }
    },
    handleBack: function() {
      if (this.currentSlide > 0) {
        this.currentSlide--
      }
    },
    handleNavIndicatorClick: function(index) {
      this.currentSlide = index;
    }
  },
  data() {
    return {
      currentSlide: 0,
      softwarePortfolio: [
        {
          title: 'Open Restaurant',
          description: 'Responsive photo gallery for a restaurant review app',
          details: 'Welcome to the photos module for Open Restaurant! The photos module presents the user with an image gallery for a given restaurant. The photos module enables full-screen modal viewing of each gallery photo with responsive sizing, associated photo details, and intuitive navigation of gallery photos. The "restaurant_id" is determined by the 1-8 digit number included at the end of the url. When the gallery page component mounts, the restuarant_id is sent in a GET request to an Express server that queries a MongoDB database for image urls of photos stored on Amazon Web Services.',
          stack: ' HTML, CSS, Javascript, React, Styled-Components, Express, MongoDB, Faker, Jest, Enzyme',
          image: require('../images/restaurant.jpg'),
          github: 'https://github.com/krummurk/photos-module'
        },
        {
          title: 'Social Inn',
          description: 'Scaled the back end of a rental accommodations app',
          details: 'Social-Inn is an online marketplace for users to book or offer lodging. This module displays all reviews associated with a particular room. I scaled this module\'s back end to handle 10 million records and 100 requests per second. I benchmarked performance of a SQL vs. NoSQL database with 10M records to determine optimal database. I deployed app on AWS and stress tested server to identify performance bottlenecks.',
          stack: 'PostgreSQL, Cassandra, Express, Amazon Web Services, k6, New Relic',
          image: require('../images/bed.jpg'),
          github: 'https://github.com/social-inn/Reviews'
        },
        {
          title: 'Connect Four',
          description: 'Game in which two players drop discs into slots and connect four to win',
          details: 'This app is modeled after the popular "Connect Four" game published by Milton Bradley in 1974 in which two players alternate dropping pieces into a 7x7 board trying to occupy 4 adjacent spaces. The app utilizes CSS animations and a dynamically rendering board (based on a two dimensional array), game status, head-to-head score, and rematch button.',
          stack: 'HTML, CSS, Javascript, React',
          image: require('../images/connect-four.png'),
          github: 'https://github.com/matt-violet/connect4'
        },
        {
          title: 'My Bolus',
          description: 'Calculating the proper dose of insulin can be tough for diabetics. My Bolus makes it easy!',
          details: 'This app simulates modern insulin pump technology by implementing a complex algorithm allowing users to calculate their bolus based on meal choice, current blood glucose (bg) level, insulin-to-carb ratio, bg correction factor, future exercise plans, and other factors.',
          stack: 'HTML, CSS, Javascript, React, Express, MongoDB',
          image: require('../images/vial.jpg'),
          github: 'https://github.com/matt-violet/My-Bolus'
        }
      ]
    }
  }
}
</script>

<style scoped>
  h2 {
    margin: 0;
    padding-bottom: 3px;
  }
  p {
    line-height: 1.2;
    margin: 5px 0px;
  }
  .software-carousel-component {
    width: 480px;
    height: 380px;
    position: relative;
    margin: 0 auto;
    background: white;
    border-radius: 10px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.4), 0 6px 20px 0 rgba(0, 0, 0, 0.4);
   }
  .track-container {
    height: 100%;
  }
  .img-div {
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
    width: 100%;
    height: 63%;
    overflow: hidden;
    border-bottom: 1px solid gray;
  }
  .img {
    min-width: 100%;
    height: 100%;
    object-fit: fill;
  }
  .img:hover {
    cursor: pointer;
  }
  .software-text-div {
    padding: 15px;
  }
  .arrow {
    position: absolute;
    top: 50%;
    width: 15px;
  }
  .arrow:hover {
    cursor: pointer;
  }
  .back {
    left: -40px;
  }
  .next {
    right: -40px;
  }
  .carousel-nav {
    height: 40px;
    width: 100%;
    text-align: center;
    position : absolute;
    bottom: 0;
  }
  .carousel-indicator {
    background: lightgray;
    width: 15px;
    height: 15px;
    border-radius: 50%;
    margin: 5px;
  }
  .carousel-indicator:hover {
    cursor: pointer;
  }
  .carousel-indicator.current-slide {
    background: gray;
  }
</style>