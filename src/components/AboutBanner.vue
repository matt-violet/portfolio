<template>
  <div class="home-component" id="home">
    <div class="left">
      <img src="../images/matt-violet.png" class="left-side-img" data-aos="fade-up" data-aos-delay='800'>
    </div>
    <div class="right">
      <div class="right-side-text" data-aos="fade-left" data-aos-delay='1000'>
        <h1 class='name'>
          Hi, I'm Matt.
        </h1>
        <p class='home-blurb'>
          &#x1F44B; I'm a multitalented human with a passion for building digital products that help others.
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
    background-image: linear-gradient(to right,  rgba(138,118,249,1), rgba(75,252,235,1));
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
    height: 90%;
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
    font-size: 70px;
    margin: 0;
  }
  .title {
    font-size: 26px;
    margin: 0;
  }
  .home-blurb {
    font-size: 20px;
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
  @media (max-width: 1200px) {
    .name {
      margin-top: 10px;
      font-size: 50px;
    }
    .home-blurb {
      font-size: 16px;
    }
    .home-component, .left, .right {
      height: 300px;
    }
    .left-side-img {
      /* height: 85%; */
    }
  }
</style>
