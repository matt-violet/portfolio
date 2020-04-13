<template>
  <div class="animatedParent" v-if='projects[currentSlide]'>
      <img class="arrow back" src="../images/left-arrow.png" v-on:click="handleBack">
    <div class="carousel animated pulse">
      <div class="track-container">
        <div class='video-div'>
          <iframe
            :src="projects[currentSlide].url"
            class="video"
            width="100%"
            height="100%"
            frameborder="0"
            allow="autoplay; fullscreen"
            allowfullscreen
          ></iframe>
        </div>
        <div class='video-text-div'>
          <h2>{{ projects[currentSlide].title }}</h2>
          <p>{{ projects[currentSlide].description }}</p>
        </div>
        <div class="carousel-nav">
          <button class="carousel-indicator" :class="currentSlide === 0 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(0)"/>
          <button class="carousel-indicator" :class="currentSlide === 1 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(1)"/>
          <button class="carousel-indicator" :class="currentSlide === 2 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(2)"/>
        </div>
      </div>
    </div>
        <img class="arrow next" src="../images/right-arrow.png" v-on:click="handleNext">
  </div>
</template>

<script>
export default {
  name: 'CarouselVideo',
  props: {
    videoProjects: { type: Array },
  },
  data() {
    return {
      currentSlide: 0,
      projects: []
    }
  },
  mounted() {
    this.$data.projects = this.videoProjects
  },
  methods: {
    handleNext: function() {
      if (this.currentSlide < 2) {
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
}
</script>

<style scoped>
  h2 {
    margin: 0;
    padding-bottom: 3px;
  }
  p {
    margin: 10px 0px;
    color: grey;
  }
  .carousel {
    width: 600px;
    position: relative;
    margin: 0 auto;
    border-bottom-left-radius: 10px;
    border-bottom-right-radius: 10px;
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.4), 0 6px 20px 0 rgba(0, 0, 0, 0.4);
    overflow: hidden;
  }
  .track-container {
    height: 100%;
    overflow: hidden;
  }
  .video-div {
    overflow: hidden;
    animation: fadeIn 1s;
    vertical-align: bottom;
    height: 335px;
  }
  .video {
    height: 100%;
  }
  .video-text-div {
    padding: 30px;
    padding-bottom: 5px;
    text-align: left;
    height: 80px;
    color: black;
  }
  .arrow {
    position: absolute;
    top: 45%;
    width: 20px;
    transition: all .2s ease-in-out;
  }
  .arrow:hover {
    cursor: pointer;
    transform: scale(1.4)
  }
  .back {
    left: 8%;
  }
  .next {
    right: 7%;
  }
  .carousel-nav {
    padding: 10px 0;
    text-align: center;
    position : relative;
  }
  .carousel-indicator {
    background: rgb(226, 226, 226);
    width: 15px;
    height: 15px;
    border-radius: 50%;
    margin: 5px;
  }
  .carousel-indicator:hover {
    cursor: pointer;
  }
  .carousel-indicator.current-slide {
    background: black;
  }
  @media (max-width: 800px) {
    .carousel {
      width: 400px;
    }
    .video-div {
      height: 225px;
    }
    .video-text-div {
      height: 40px;
      padding: 10px;
      padding-bottom: 20px;
    }
    h2 {
      font-size: 18px;
    }
    p {
      font-size: 12px;
    }
  }
</style>