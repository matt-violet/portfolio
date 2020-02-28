<template>
  <div class="carousel">
    <img class="arrow back" src="../images/left-arrow.png" v-on:click="handleBack">
    <div class="track-container">
      <div class="track-inner">
        <img
          :src="projects[currentSlide].image"
          class='img'
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
    width: 480px;
    height: 380px;
    position: relative;
    margin: 0 auto;
    border: 1px solid gray;
    /* box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.4), 0 6px 20px 0 rgba(0, 0, 0, 0.4); */
  }
  .track-container {
    margin: 0 auto;
    padding: 10px;
    height: 75%;
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
    text-align: center;
  }
  .arrow {
    position: absolute;
    top: 50%;
    width: 15px;
  }
  .arrow:hover {
    cursor: pointer;
    transform: scale(1.1);
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