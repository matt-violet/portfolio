<template>
  <div class="animatedParent">
    <div class="carousel animated pulse">
      <img class="arrow back" src="../images/left-arrow.png" v-on:click="handleBack">
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
        <img class="arrow next" src="../images/right-arrow.png" v-on:click="handleNext">
        <div class="carousel-nav">
          <button class="carousel-indicator" :class="currentSlide === 0 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(0)"/>
          <button class="carousel-indicator" :class="currentSlide === 1 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(1)"/>
          <button class="carousel-indicator" :class="currentSlide === 2 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(2)"/>
        </div>
      </div>
    </div>
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
  }
  .carousel {
    width: 600px;
    position: relative;
    margin: 0 auto;
    background: white;
   }
  .track-container {
    height: 100%;
  }
  .video-div {
    overflow: hidden;
    border-bottom: 1px solid gray;
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
    background: white;
  }
  .arrow {
    position: absolute;
    top: 45%;
    width: 20px;
  }
  .arrow:hover {
    cursor: pointer;
    transform: scale(1.4)
  }
  .back {
    left: -40px;
  }
  .next {
    right: -40px;
  }
  .carousel-nav {
    padding: 10px 0;
    text-align: center;
    position : relative;
  }
  .carousel-indicator {
    background: white;
    width: 15px;
    height: 15px;
    border: 1px solid;
    border-radius: 50%;
    margin: 5px;
  }
  .carousel-indicator:hover {
    cursor: pointer;
  }
  .carousel-indicator.current-slide {
    background: black;
  }
  @media (max-width: 1220px) {
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