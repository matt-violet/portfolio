<template>
  <div class="home-component" id="home">
    <div class="bg-div">
      <img src='../images/skate.jpg' class='bg-img-skate'>
    </div>
    <div class='header'>
      <h1 class='line1'>MATT VIOLET</h1>
      <h1 class='line2'>Software Engineer</h1>
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
    height: 600px;
    background: rgba(14, 14, 14, 0.2);
  }
  .header {
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

  }
</style>
