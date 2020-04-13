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
      <button
        v-for="(project, i) of projects"
        v-bind:key="i"
        class="carousel-indicator"
        :class="currentSlide === i ? 'current-slide' : ''"
        v-on:click="handleNavIndicatorClick(i)"
      />
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
      if (this.currentSlide < this.designProjects.length - 1) {
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
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.4), 0 6px 20px 0 rgba(0, 0, 0, 0.4);
    border-radius: 10px;
    transition: all .2s ease-in-out;
  }
  .img:hover {
    cursor: pointer;
    transform: scale(1.4);
  }
  .design-text-div {
    padding-top: 20px;
    text-align: center;
  }
  .arrow {
    position: absolute;
    width: 20px;
    transition: all .2s ease-in-out;
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
    background: rgb(226, 226, 226);
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
    .track-container {
      height: 250px;
    }
  }
</style>