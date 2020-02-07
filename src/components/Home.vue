<template>
  <div class="home-component">
    <div class='home-wrapper'>
      <img :src='pic' class='pic'/>
      <div class='words-wrapper'>
        <h1 class='words name'>{{ line1 }}</h1>
        <h4 class='words title'>{{ line2 }}</h4>
      </div>
    </div>
    <img src="../images/hills.jpg" class="bg-img"/>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
      pic: require('../images/matt-violet.png'),
      line1: "Welcome!",
      line2: "I'm Matt. Have a look around!",
    }
  }
}
</script>

<style>
  .home-wrapper {
    width: 100%;
    margin-top: 100px;
    position: absolute;
  }
  .bg-img {
    position: absolute;
    height: 100%;
    min-width: 100%;
    z-index: -1;
  }
  h1 {
    margin-top: 10px;
    margin-bottom: 0;
    text-align: center;
    font-size: 50px;
  }
  h4 {
    margin: 0;
    text-align: center;
  }
  .pic {
    height: 200px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    animation-duration: .75s;
    animation-name: slideDown;
  }
  .words {
    margin-top: 5;
  }
  .name {
    animation-duration: .75s;
    animation-name: slideLeft;
  }
  .title {
    animation-duration: .75s;
    animation-name: slideRight;
  }
  @keyframes slideDown {
    from { transform: translateY(-500px); }
    to { transform: translateY(0px); }
  }
  @keyframes slideRight {
    from { transform: translateX(-1000px); }
    to { transform: translateX(0px); }
  }
  @keyframes slideLeft {
    from { transform: translateX(1000px); }
    to { transform: translateX(0px); }
  }
</style>
