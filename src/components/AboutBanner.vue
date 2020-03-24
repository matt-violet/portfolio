<template>
  <div class="home-component" id="home">
    <div class="left">
      <img src="../images/matt-violet.png" class="left-side-img" data-aos="fade-up" data-aos-delay='300'>
    </div>
    <div class="right">
      <div class="right-side-text" data-aos="fade-left" data-aos-delay='300'>
        <h1 class='line-1'>
          Matt Violet
        </h1>
        <p class='line-2'>
          Software Engineer
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
    height: 350px;
    position: relative;
    background-image: linear-gradient(to right,  rgba(138,118,249,1), rgba(75,252,235,1));
  }
.left {
    width: 50%;
    height: 350px;
    display: inline-block;
    position: relative;
    text-align: center;
  }
  .right {
    width: 50%;
    height: 350px;
    display: inline-block;
    overflow: hidden;
  }
  .left-side-img {
    height: 80%;
    position: absolute;
    bottom: 0;
    right: 0px;
    /* -webkit-filter: drop-shadow(-4px -4px 4px #222); */
    /* filter: drop-shadow(-4px -4px 4px #222); */
  }
  .right-side-text {
    height: 120px;
    position: absolute;
    color: rgb(43, 43, 43);
    margin: 140px auto 0 auto;
  }
  .line-1 {
    font-size: 60px;
    margin: 0;
  }
  .line-2 {
    margin: 0;
    font-size: 18px;
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
  @media (max-width: 1100px) {
    .right-side-text {
      margin-top: 100px;
    }
    .line-1 {
      font-size: 40px;
    }
    .line-2 {
      font-size: 14px;
    }
    .home-component, .left, .right {
      height: 250px;
    }
    .left-side-img {
      /* height: 300px; */
    }
  }
</style>
