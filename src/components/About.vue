<template>
  <div class="about-wrapper">
    <AboutBanner class="about-banner"/>
    <div class="about-component" data-aos="flip-up">
      <div class="about-me" data-aos="zoom-in" data-aos-delay='100'>
        <h1 class='about-header'>My Story</h1>
        <p class='bio-text'>
          Born and raised in Oakland, CA and a UC Davis graduate, I dedicated the first chapter of my career to non-profit marketing / communications work, supporting various communities both at home and abroad.
        </p>
        <p class='bio-text'>
          My interest in programming came in 2015, at a turning point in my life. Shortly after I was diagnosed with type one diabetes, I started wearing two electronic medical devices that worked together to create a hybrid closed-loop system to help manage my blood sugar levels. With my health now literally tied to automated algorithms, I have a new appreciation for the power of code.
        </p>
        <p class='bio-text'>
          Understanding what technological innovation has done for me, and can do for others, is what drives me to take on complex challenges, hunt for new skills, and think big.
        </p>
      </div>
    </div>
    <div class='about-imgs'>
      <img src='../images/matt-guitar.jpg' class='about-img'>
      <img src='../images/maesot.jpg' class='about-img'>
      <img src='../images/matt-cgm.jpg' class='about-img'>
      <img src='../images/skate.jpg' class='about-img'>
      <img src='../images/matt-as.jpg' class='about-img'>
    </div>
    <Skills class="skills"/>
  </div>
</template>

<script>
import AboutBanner from './AboutBanner.vue'
import Skills from './Skills.vue'

export default {
  name: 'about',
  components: {
    AboutBanner,
    Skills,
  },
}
</script>

<style>
  .about-wrapper {
    background-image: linear-gradient( to right, rgba(138,118,249,1), rgba(75,252,235,1));
    background-repeat: no-repeat;
    height: 100%;
    padding-bottom: 100px;
  }
  .about-banner {
    z-index: 0;
    position: relative;
  }
  .about-component {
    background: hsl(0, 0%, 100%);
    position: relative;
    z-index: 2;
    width: 70%;
    margin: 0 auto;
    border: 1px solid gray;
  }
  .about-imgs {
    width: 100%;
    position: relative;
    z-index: 2;
    text-align: center;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.4), 0 6px 20px 0 rgba(0, 0, 0, 0.4);
    border-top: 1px solid rgb(43, 43, 43);
    border-bottom: 1px solid rgb(43, 43, 43);
  }
  .about-img {
    width: 20%;
    height: 100%;
    display: inline-block;
    vertical-align: bottom;
  }
  .about-me {
    margin: 0 auto;
    padding: 60px 80px;
    max-width: 650px;
  }
  .about-header {
    margin: 20px auto 0 auto;
    padding-bottom: 40px;
    text-align: center;
    font-size: 28px;
  }
  .bio-text {
    margin: 0 0 20px 0;
    font-size: 16px;
    display: inline-block;
  }
</style>