<template>
  <div class="carousel">
    <img class="arrow back" src="../images/left-arrow.png" v-on:click="handleBack">
    <div class="track-container">
      <div class='img-div'>
        <iframe
          :src="videoPortfolio[currentSlide].url"
          width="100%"
          height="100%"
          frameborder="0"
          allow="autoplay; fullscreen"
          allowfullscreen
        ></iframe>
      </div>
      <div class='text-div'>
        <h2>{{ videoPortfolio[currentSlide].title }}</h2>
        <p>{{ videoPortfolio[currentSlide].description }}</p>
      </div>
    </div>
    <img class="arrow next" src="../images/right-arrow.png" v-on:click="handleNext">
    <div class="carousel-nav">
      <button class="carousel-indicator" :class="currentSlide === 0 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(0)"></button>
      <button class="carousel-indicator" :class="currentSlide === 1 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(1)"></button>
      <button class="carousel-indicator" :class="currentSlide === 2 ? 'current-slide' : ''" v-on:click="handleNavIndicatorClick(2)"></button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CarouselSoftware',
  props: {
    viewProjectDetails: { type: Function },
    project: { type: Object },
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
  data() {
    return {
      currentSlide: 0,
      videoPortfolio: [
        {
          title: 'Soaring Sunday',
          description: 'Join me in the clouds and learn about soaring as I fly over Byron, CA in this meditative-like weekend recap video.',
          url: "https://player.vimeo.com/video/118749275"
        },
        {
          title: 'Starr King Threshold Ceremony',
          description: 'Watch as the Starr King community formally welcomes new students to the school.',
          url: 'https://www.youtube.com/embed/Boi3G8wiEAY'
        },
        {
          title: 'A Mindful Walk: Immersion Course',
          description: 'Experience Transylvania\'s hills and river valleys, cultural sites, music, dance, and community in this unforgettable immersion couse.',
          url: 'https://www.youtube.com/embed/6eKqxxVSlKQ'
        }
      ],
    }
  }
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
  .text-div {
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