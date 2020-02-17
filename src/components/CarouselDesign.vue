<template>
  <div class="carousel">
    <img class="arrow back" src="../images/left-arrow.png" v-on:click="handleBack">
    <div class="track-container">
      <div class="track-inner">
        <img
          :src="designPortfolio[currentSlide].image"
          class='img'
          v-on:click="$emit('viewProjectDetails', designPortfolio[currentSlide])"
        />
      </div>
    </div>
    <div class="design-text-div">
      <p>{{ designPortfolio[currentSlide].description }}</p>
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
    </div>
  </div>
</template>

<script>
export default {
  name: 'CarouselDesign',
  props: {
    viewProjectDetails: { type: Function },
    project: { type: Object },
  },
  methods: {
    handleNext: function() {
      if (this.currentSlide < 6) {
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
  data() {
    return {
      currentSlide: 0,
      designPortfolio: [
        {
          image: require('../images/Symposium2019.jpg'),
          description: 'Event Flyer, 2019',
          design: true
        },
        {
          image: require('../images/GA2017.png'),
          description: 'Recruitment Flyer, 2018',
          design: true
        },
        {
          image: require('../images/SKSM-banner.jpg'),
          description: '8-foot Retractable Banner, 2017',
          design: true
        },
        {
          image: require('../images/GA2016-flyer.png'),
          description: 'Ad in UU World Magazine, 2016',
          design: true
        },
        {
          image: require('../images/GA2017-flyer.png'),
          description: 'Ad in UU World Magazine, 2017',
          design: true
        },
        {
          image: require('../images/GA2018-flyer.png'),
          description: 'Ad in UU World Magazine, 2018',
          design: true
        },
        {
          image: require('../images/SEAsia.png'),
          description: 'Graphic for Personal Project, 2015',
          design: true
        },
      ]
    }
  }
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
    background: white;
    border-radius: 10px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.4), 0 6px 20px 0 rgba(0, 0, 0, 0.4);
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
    /* padding: 15px; */
    text-align: center;
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