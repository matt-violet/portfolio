<template>
  <div class="about-wrapper">
    <AboutBanner class="about-banner"/>
    <div class="about-component" data-aos="flip-up">
      <h1 class='about-header'>My Story</h1>
      <div class="about-me" data-aos="zoom-in" data-aos-delay='100'>
        <p class='bio-text'>
          Born and raised in Oakland, CA and a graduate of UC Davis, I dedicated the first chapter of my career to non-profit marketing / communications, where I gained exposure to HTML, WordPress, and SEO maintaining websites.
        </p>
        <p class='bio-text'>
          I developed a stronger interest in programming in 2015. Shortly after my type one diabetes diagnosis I got my first "artificial pancreas", two electronic medical devices that worked together in a hybrid closed-loop system to manage my blood sugar levels. I was -- and still am -- fascinated by these devices. I'm equally fascinated by the "hacker communities" that decided <a href='https://openaps.org/' target='blank'>#WeAreNotWaiting</a> and paved the way to make this technology as safe and widely available as possible, years before the first commercial closed loops sytems. Details on the evolution of the "artificial pancreas" and my journey into coding are included in my informal presentation <a href='https://drive.google.com/file/d/1D8tp35PoCCbMzuWLTPHFI5oGN7nFhIQ1/view?usp=sharing' target='_blank'>Tech Innovation and T1D Care</a>.
        </p>
        <p class='bio-text'>
          With my health now literally tied to algorithms, I'm steadily reminded of the limitless possibilities of code and inspired to be the best developer I can be.
        </p>
      </div>
    </div>
    <div class='about-imgs'>
      <img src='../images/matt-guitar.jpg' class='about-img'>
      <div class="overlay">
        <div class="overlay-text">
          On a solo gap year in Southeast Asia 🌏
        </div>
      </div>
      <img src='../images/maesot.jpg' class='about-img'>
      <div class="overlay">
        <div class="overlay-text">
          Working with Burmese migrant communities in Thailand 💪
        </div>
      </div>
      <img src='../images/using-pump.jpg' class='about-img'>
      <div class="overlay">
        <div class="overlay-text">
          Texting my artificial pancreas 📲
        </div>
      </div>
      <img src='../images/skate.jpg' class='about-img'>
      <div class="overlay">
        <div class="overlay-text">
          Keep pushing, it will all be worth it 🏆
        </div>
      </div>
      <img src='../images/matt-as.jpg' class='about-img'>
      <div class="overlay">
        <div class="overlay-text">
          Rooted in Oakland 🌳
        </div>
      </div>
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
    background: linear-gradient( to right, rgba(138,118,249,1), rgba(75,252,235,1));
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
    border-top-right-radius: 10px;
    border-top-left-radius: 10px;
    overflow: hidden;
    position: relative;
    z-index: 2;
    width: 70%;
    margin: 0 auto;
    border: 1px solid gray;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.4), 0 6px 20px 0 rgba(0, 0, 0, 0.4);
  }
  .about-me {
    margin: 0 auto;
    padding: 40px 120px;
    color: darkslategrey;
  }
  .about-header {
    margin: 0;
    padding: 50px 0;
    text-align: center;
    font-size: 32px;
    background: linear-gradient( to left, rgba(138,118,249,.5), rgba(75,252,235,.5));
  }
  .bio-text {
    margin: 0 0 20px 0;
    font-size: 16px;
    display: inline-block;
  }
  .about-imgs {
    width: 100%;
    height: 20vw;
    position: relative;
    z-index: 2;
    text-align: center;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.4), 0 6px 20px 0 rgba(0, 0, 0, 0.4);
    border-top: 1px solid rgb(43, 43, 43);
    border-bottom: 1px solid rgb(43, 43, 43);
  }
  .about-img {
    width: 20%;
    position: absolute;
  }
  /* ----------------------- OVERLAY ----------------------- */
  .overlay-text {
    color: white;
    font-size: 12px;
    width: 20vw;
    top: 50%;
    position: absolute;
  }
  .overlay {
    display: inline-block;
    vertical-align: middle;
    height: 20vw;
    width: 20vw;
    opacity: 0;
    transition: 0.5s ease;
    background-color: black;
  }
  .overlay:hover {
    opacity: 0.8;
  }
  @media (max-width: 1100px) {
    .about-component {
      width: 100%;
      border-radius: 0;
    }
    .about-wrapper {
      padding-bottom: 0;
    }
    .overlay-text {
      font-size: 10px;
    }
  }
</style>