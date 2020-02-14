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
    margin-left: auto;
    margin-right: auto;
    height: 500px;
    text-align: center;
    position: relative;
    justify-content: center;
  }
  .headers-div {
    text-align: center;
  }
  .photo {
    width: 200px;
    border-radius: 50%;
    background-color: white;
  }
  .line1 {
    font-size: 30px;
    margin: 0;
  }
  .line2 {
    font-size: 15px;
    line-height: 15px;
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
