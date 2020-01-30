<template>
  <div class="about-wrapper">
    <div class="split left-side">
      <div class="centered">
        <img :src="aboutPic" class="aboutPic"/>
      </div>
    </div>
    <div class="split right-side">
      <div class="centered">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'About',
  data() {
    return {
      aboutPic: require('../images/matt-taj.jpg')
    }
  }
}
</script>

<style scoped>
  .split {
    height: 100%;
    width: 50%;
    position: fixed;
    z-index: 1;
    top: 0;
    overflow-x: hidden;
  }
  .left-side {
    left: 0;
    background-color: gainsboro;
  }
  .right-side {
    right: 0;
    background-color: gray;
  }
  .centered {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    text-align: center;
    width: 200px;
    height: 200px;
  }
  .aboutPic {
    width: 100%;
  }
</style>