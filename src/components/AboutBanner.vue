<template>
  <div class="home-component" id="home">
    <div class="left animatedParent">
      <img src="../images/matt-violet.png" class="left-side-img animated slideInUp">
    </div>
    <div class="right animatedParent">
      <div class="right-side-text animated slideInDown">
        <h1 class='name'>
          Hi, I'm Matt. &#x1F44B;
        </h1>
        <p class='home-blurb'>
          I'm a multitalented human with a passion for designing and building digital products that help others.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AboutBanner',
}
</script>

<style>
  .home-component {
    padding-top: 52px;
    width: 100%;
    height: 400px;
    position: relative;
    /* background-image: linear-gradient(120deg, #e0c3fc 0%, #8ec5fc 100%); */
    background-image: linear-gradient(to right, #eea2a2 0%, #bbc1bf 19%, #57c6e1 42%, #b49fda 79%, #7ac5d8 100%);
    /* background-image: linear-gradient(to top, #d5dee7 0%, #ffafbd 0%, #c9ffbf 100%); */
    /* background-image: linear-gradient(-225deg, #2CD8D5 0%, #C5C1FF 56%, #FFBAC3 100%); */
    /* background-image: linear-gradient(to right, #00dbde 0%, #fc00ff 100%); */
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
    overflow: hidden;
  }
  .left-side-img {
    height: 85%;
    margin: auto;
    position: absolute;
    bottom: 0;
    right: 0;
    /* -webkit-filter: drop-shadow(-4px -4px 4px #222); */
    /* filter: drop-shadow(-4px -4px 4px #222); */
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
</style>
