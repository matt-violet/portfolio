<template>
  <div class="about-wrapper">
    <AboutBanner class="about-banner"/>
    <div class="about-component">
      <div class="about-me">
        <h1 class='about-header'>About Me</h1>
        <p class='bio-text'>
          Native of Oakland, CA, I have a big heart and I bring passion to everything I do. I dedicated the first chapter of my career to non-profit marketing / communications work, supporting various communities both at home and abroad.
        </p>
        <p class='bio-text'>
          My interest in software came in 2015, at a time of major change in my life. Shortly after I was diagnosed with type one diabetes, I started wearing two electronic medical devices that worked together to create a hybrid closed-loop system to help manage my blood sugar levels. As someone whose health is now literally tied to automated algorithms, my appreciation for the power of code has changed forever.
        </p>
        <p class='bio-text'>
          Understanding what technological innovation has done for me, and can do for others, is what motivates me to dream big, learn new things, and tackle complex problems. 
        </p>
      </div>
    </div>
    <div class='about-imgs'>
      <img src='../images/matt-guitar.jpg' class='about-img'>
      <img src='../images/maesot.jpg' class='about-img'>
      <img src='../images/matt-cgm.jpg' class='about-img'>
      <img src='../images/sksm.jpg' class='about-img'>
      <img src='../images/matt-dubs.jpg' class='about-img'>
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
  }
}
</script>

<style>
  .about-wrapper {
    background-image: linear-gradient(to right, #eea2a2 0%, #bbc1bf 19%, #57c6e1 42%, #b49fda 79%, #7ac5d8 100%);
    background-repeat: no-repeat;
    height: 100%;
  }
  .skills {
    margin-top: -5px;
    padding-bottom: 100px;
  }
  .about-banner {
    z-index: 0;
    position: relative;
  }
  .about-component {
    position: relative;
    z-index: 2;
    width: 1000px;
    margin: 0 auto;
    background: white;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.4), 0 6px 20px 0 rgba(0, 0, 0, 0.4);
  }
  .about-imgs {
    width: 100%;
    position: relative;
    z-index: 2;
    text-align: center;
  }
  .about-img {
    width: 20%;
    height: 100%;
    display: inline-block;
  }
  .about-me {
    width: 600px;
    margin: 0 auto;
    padding: 40px;
  }
  .about-header {
    margin: 0 auto;
    padding-bottom: 40px;
    text-align: center;
    font-size: 25px;
  }
  .bio-text {
    margin: 0 0 20px 0;
    font-size: 14px;
    display: inline-block;
  }
</style>