<template>
  <div class="about-wrapper">
    <AboutBanner class="about-banner"/>
    <div class="about-component" data-aos="flip-up">
      <h1 class='about-header'>My Story</h1>
      <div class="about-me" data-aos="zoom-in" data-aos-delay='100'>
        <p class='bio-text'>
          <strong>I never could have anticipated my journey into software development,</strong> but now I can't see myself doing anything else.
        </p>
        <p class='bio-text'>
          Although my professional path has taken many twists and turns — from tutoring students of East Oakland's underserved schools, to empowering Burmese migrants in Thailand, to establishing a new communications department for an activist non-profit in Berkeley — <strong>I've always followed my passion</strong> to help others and solve problems.</p>
        <p class='bio-text'>
          My passion for programming comes from the role software plays in my personal health, as a <strong>self-identified <a href='https://drive.google.com/file/d/1D8tp35PoCCbMzuWLTPHFI5oGN7nFhIQ1/view?usp=sharing' target='_blank'>human cyborg</a> who has used an "artificial pancreas" to manage his type one diabetes since 2016.</strong> With my daily well-being now literally tied to algorithms, I'm invested in learning and developing applications that have the potential to help others as much as these devices have helped me.
        </p>
        <p class='bio-text'>
          When not coding I can be found DJing, making Photoshop creations, and social distancing in my hometown of Oakland, CA.
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
    padding: 50px 120px;
    font-weight: 400;
    /* color: grey; */
  }
  .about-header {
    margin: 0;
    padding: 80px 0;
    text-align: center;
    font-size: 32px;
    font-weight: 700;
    background: linear-gradient(to left, rgba(138,118,249,.5), rgba(75,252,235,.5));
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
    opacity: 0.7;
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