<template>
  <div class="home-component" id="home">
    <img src='../images/oak-sunset.jpg' class='oak-sunset'>
    <div class='header'>
      <h1 class='line1'>Matt Violet</h1>
      <h1 class='line2'>Designer | Software Engineer | Videographer</h1>
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
    /* background: lightblue; */
    padding-bottom: 90px;
    height: 540px;
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
    font-size: 50px;
    margin: 0;
  }
  .line2 {
    margin: 0;
    font-size: 15px;
  }
  .matt-oak {
    width:  100%;
    display: flex;
    bottom: 0;
    margin: 0 auto;
    position: relative;
  }
  .oak-sunset {
    min-width: 100%;
    height: 630px;
    position: absolute;
    /* opacity: .9; */
    z-index: -1;
  }
</style>
