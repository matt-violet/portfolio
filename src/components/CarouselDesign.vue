<template>
  <div class="carousel" v-if='projects[currentSlide]'>
    <img class="arrow back" src="../images/left-arrow.png" v-on:click="handleBack">
    <div class="track-container">
      <div class="track-inner">
        <img
          :src="projects[currentSlide].image"
          class='img animated pulse'
          v-on:click="$emit('viewProjectDetails', projects[currentSlide])"
        />
      </div>
    </div>
    <div class="design-text-div">
      <p>{{ projects[currentSlide].description }}</p>
    </div>
    <img class="arrow next" src="../images/right-arrow.png" v-on:click="handleNext">
    <div class="carousel-nav">
      <button class="carousel-indicator" :class="currentSlide === 0 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(0)"/>
      <button class="carousel-indicator" :class="currentSlide === 1 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(1)"/>
      <button class="carousel-indicator" :class="currentSlide === 2 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(2)"/>
      <button class="carousel-indicator" :class="currentSlide === 3 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(3)"/>
      <button class="carousel-indicator" :class="currentSlide === 4 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(4)"/>
      <button class="carousel-indicator" :class="currentSlide === 5 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(5)"/>
      <button class="carousel-indicator" :class="currentSlide === 6 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(6)"/>
      <button class="carousel-indicator" :class="currentSlide === 7 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(7)"/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CarouselDesign',
  props: {
    viewProjectDetails: { type: Function },
    designProjects: { type: Array },
  },
  data() {
    return {
      currentSlide: 0,
      projects: []
    }
  },
  mounted() {
    this.$data.projects = this.designProjects
  },
  methods: {
    handleNext: function() {
      if (this.currentSlide < 7) {
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
  }
  p {
    margin:  0;
    line-height: 1.5;
  }
  .carousel {
    position: relative;
    margin: auto;
  }
  .track-container {
    margin: 0 auto;
    padding: 10px;
    height: 500px;
    display: flex;
    align-items: center;
  }
  .track-inner {
    height: 100%;
    display: flex;
    align-items: center;
    text-align: center;
    margin: auto;
  }
  .img {
    max-width: 100%;
    max-height: 100%;
    object-fit: fill;
  }
  .img:hover {
    cursor: pointer;
  }
  .design-text-div {
    margin: 40px 0 0 0;
    text-align: center;
    color: darkslategray;
  }
  .arrow {
    position: absolute;
    width: 20px;
  }
  .arrow:hover {
    cursor: pointer;
    transform: scale(1.4);
  }
  .back {
    left: -30px;
    top: 40%;
  }
  .next {
    right: -30px;
    top: 40%;
  }
  .carousel-nav {
    width: 100%;
    margin-top: 10px;
    text-align: center;
  }
  .carousel-indicator {
    background: white;
    height: 15px;
    border: 1px solid;
    border-radius: 50%;
    margin: 5px;
  }
  .carousel-indicator:hover {
    cursor: pointer;
  }
  .carousel-indicator.current-slide {
    background: darkslategrey;
  }
  @media (max-width: 800px) {
    .track-container {
      height: 250px;
    }
  }
</style>