<template>
  <div class="home-component" id="home">
    <div class="left animatedParent">
      <img src="../images/matt-violet.png" class="left-side-img animated bounceInLeft">
    </div>
    <div class="right animatedParent">
      <div class="right-side-text animated bounceInDown">
        <h1 class='name'>
          Matt Violet
        </h1>
        <h3 class='title'>
          Software Engineer
        </h3>  
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
    height: 450px;
    background: linear-gradient(180deg, hsl(248, 55%, 56%), hsl(256, 59%, 26%));
    position: relative;
    border-bottom-right-radius: 30%;
  }
  .left {
    width: 50%;
    height: 450px;
    display: inline-block;
    position: relative;
    text-align: center;
    ;
  }
  .right {
    width: 50%;
    height: 450px;
    display: inline-block;
    z-index: 2;
    overflow: hidden;
  }
  .left-side-img {
    height: 85%;
    margin: auto;
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    z-index: 1;
    /* -webkit-filter: drop-shadow(-8px -4px 8px #222);
    filter: drop-shadow(-8px -4px 8px #222); */
  }
  .right-side-text {
    width: 300px;
    height: 100px;
    position: absolute;
    top: 0;
    bottom: 0;
    color: white;
    margin: auto;
  }
  .name {
    font-size: 50px;
    margin: 0;
  }
  .title {
    font-size: 20px;
    margin: 0;
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
