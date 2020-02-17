<template>
  <div class="home-component" id="home">
    <div class="bg-div">
      <img src='../images/oak-sunset.jpg' class='oak-sunset'>
    </div>
    <div class='header'>
      <h1 class='line1'>Matt Violet</h1>
      <h1 class='line2'>Designer | Software Engineer | Videographer</h1>
      <h1 class='line2'>Oakland, CA</h1>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
}
</script>

<style>
  .home-component {
    width: 100%;
    height: 590px;
  }
  .header {
    text-align: center;
    margin: 90px 70px;
    color: white;
    display: inline-block;
  }
  .photo {
    width: 170px;
    border-radius: 50%;
    border: 1px solid gray;
    background-color: lightsalmon;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.4), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  }
  .line1 {
    font-size: 42px;
    margin: 0;
  }
  .line2 {
    margin: 0;
    font-size: 13px;
    line-height: 22px;
  }
  .bg-div {
    width: 100%;
    height: 590px;
    position: absolute;
  }
  .oak-sunset {
    min-width: 100%;
    height: 590px;
    position: absolute;
    z-index: -1;
    position: fixed;
  }
</style>
