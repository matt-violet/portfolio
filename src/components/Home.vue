<template>
  <div class="home-component" id="home">
    <div class="left animatedParent">
      <img src="../images/matt-violet.png" class="left-side-img animated slideInLeft">
    </div>
    <div class="right animatedParent">
      <div class="right-side-text animated slideInDown">
        <h1 class='name'>
          Hi, I'm Matt. &#x1F44B;
        </h1>
        <!-- <h3 class='title'>
          Software Engineer
        </h3>   -->
        <p class='home-blurb'>
          I'm a multitalented human with a passion for designing and building digital products that help others.
        </p>
      </div>
    </div>

    <!-- <div class="bg-div">
      <img src='../images/skate.jpg' class='bg-img-skate'>
    </div>
    <div class='header'>
      <h1 class='line1'>MATT VIOLET</h1>
      <h1 class='line2'>Software Engineer</h1>
    </div> -->
  </div>
</template>

<script>
export default {
  name: 'Home',
}
</script>

<style>
  .home-component {
    padding-top: 52px;
    width: 100%;
    height: 400px;
    position: relative;
    /* background-image: linear-gradient(120deg, #e0c3fc 0%, #8ec5fc 100%); */
/* background-image: linear-gradient(to right, #43e97b 0%, #38f9d7 100%); */
background-image: linear-gradient(to right, #eea2a2 0%, #bbc1bf 19%, #57c6e1 42%, #b49fda 79%, #7ac5d8 100%);
/* background-image: linear-gradient(-225deg, #D4FFEC 0%, #57F2CC 48%, #4596FB 100%); */
  }
.left {
    width: 50%;
    height: 400px;
    display: inline-block;
    position: relative;
    text-align: center;
  }
  .right {
    width: 50%;
    height: 400px;
    display: inline-block;
    z-index: 2;
    overflow: hidden;
  }
  .left-side-img {
    height: 85%;
    margin: auto;
    position: absolute;
    bottom: 0;
    /* left: 0; */
    right: 0;
    z-index: 1;
    /* -webkit-filter: drop-shadow(-8px -4px 8px #222);
    filter: drop-shadow(-8px -4px 8px #222); */
  }
  .right-side-text {
    width: 400px;
    height: 100px;
    position: absolute;
    top: 0;
    bottom: 0;
    color: rgb(43, 43, 43);
    margin: auto;
  }
  .name {
    font-size: 50px;
    margin: 0;
  }
  .title {
    font-size: 26px;
    margin: 0;
  }
  .home-blurb {
    /* margin-top: 40px; */
    font-size: 16px;
  }
  @keyframes gradient {
    0% {
      background-position: 0% 50%;
    }
    50% {
      background-position: 100% 50%;
    }
    100% {
      background-position: 0% 50%;
    }
  }
  /* .header {
    margin: 70px 30px;
    color: black;
    display: inline-block;
    padding: 10px;
  }
  .line1 {
    font-size: 22px;
    margin: 0;
    color: lightgray;
  }
  .line2 {
    margin: 0;
    font-size: 12px;
    color: lightgray;
  }
  .bg-div {
    width: 100%;
    height: 600px;
    position: absolute;
  }
  .bg-img-skate {
    vertical-align: middle;
    min-width: 100%;

    height: 600px;
    position: absolute;
    z-index: -1;
    position: fixed;

  } */
</style>
