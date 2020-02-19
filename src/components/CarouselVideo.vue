<template>
  <div class="carousel">
    <img class="arrow back" src="../images/left-arrow.png" v-on:click="handleBack">
    <div class="track-container">
      <div class='img-div'>
        <iframe
          :src="projects[currentSlide].url"
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
    </div>
    <img class="arrow next" src="../images/right-arrow.png" v-on:click="handleNext">
    <div class="carousel-nav">
      <button class="carousel-indicator" :class="currentSlide === 0 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(0)"/>
      <button class="carousel-indicator" :class="currentSlide === 1 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(1)"/>
      <button class="carousel-indicator" :class="currentSlide === 2 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(2)"/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CarouselVideo',
  props: {
    viewProjectDetails: { type: Function },
    videoProjects: { type: Object },
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
    line-height: 1.2;
    margin: 5px 0px;
  }
  .carousel {
    width: 480px;
    height: 422px;
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
    height: 64%;
    width: 100%;
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
  .video-text-div {
    padding: 15px;
    height: 30%;
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