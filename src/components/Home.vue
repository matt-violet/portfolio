<template>
  <div class="home-component" id="home">
    <img class="photo" src="../images/matt-violet.png"/>
    <div class='headers-div'>
      <h1 class='line1'>Matt Violet</h1>
      <h1 class='line2'>Software engineer</h1>
    </div>
    <div class='down-arrow-div'>
      <img src="../images/down-arrow.png"
        onClick="document.getElementById('about').scrollIntoView({ behavior: 'smooth' })"
        class="down-arrow"
      />
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
    padding-top: 160px;
    margin-bottom: 100px;
    margin-left: auto;
    margin-right: auto;
    height: 500px;
    text-align: center;
    position: relative;
    justify-content: center;
    background: lightblue;
  }
  .headers-div {
    text-align: center;
  }
  .photo {
    width: 200px;
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
    font-size: 18px;
    line-height: 5px;
    text-align: center;
  }
  .down-arrow-div {
    position: absolute;
    bottom: 0;
    width: 100%;
  }
  .down-arrow {
    margin: 0 auto;
    height: 20px;
  }
  .down-arrow:hover {
    cursor: pointer;
    transform: scale(1.2);
  }
</style>
