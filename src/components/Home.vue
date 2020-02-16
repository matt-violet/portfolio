<template>
  <div class="home-component" id="home">
    <div class='home-inner'>
      <div class='header'>
        <h1 class='line1'>Matt Violet</h1>
        <h1 class='line2'>Designer | Software Engineer | Videographer</h1>
      </div>
      <div class="img-div">
        <img src='../images/matt-oak-blank.png' class='matt-oak'>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
}
</script>

<style>
  td {
    padding: 0 10px;
  }
  .home-component {
    background: lightblue;
    padding-bottom: 90px;
    height: 540px;
  }
  .home-inner {
    padding-top: 40px;
    width: 500px;
    margin: 0 auto 0 auto;
  }
  .header {
    text-align: center;
    padding-bottom: 30px;
  }
  .bio {
    margin: 50px auto;
    width: 500px;
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
    font-size: 16px;
    text-align: center;
  }
  .img-div {
    margin: 0 auto;
    width: 350px;
  }
  .matt-oak {
    width:  100%;
    display: flex;
    bottom: 0;
    margin: 0 auto;
  }
</style>
