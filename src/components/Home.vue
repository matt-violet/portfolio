<template>
  <div id='home-wrapper'>
    <img :src='pic' id='pic'/>
    <div class='words-wrapper'>
      <h1 class='words name'>{{ name }}</h1>
      <h4 class='words title'>{{ title }}</h4>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
      pic: require('../images/matt-violet.jpg'),
      title: "Welcome to my page!",
      name: "I'm Matt."
    }
  }
}
</script>

<style>
  #home-wrapper {
    margin-left: auto;
    margin-right: auto;
    width: 250px;
  }
  h1 {
    margin-top: 10px;
    margin-bottom: 0;
    text-align: center;
  }
  h4 {
    margin: 0;
    text-align: center;
  }
  #pic {
    height: 200px;
    border-radius: 50%;
    border: 1px solid;
    display: block;
    margin-left: auto;
    margin-right: auto;
    animation-duration: .75s;
    animation-name: slideDown;
  }
  #titleSection {
    text-align: center;
    width: 250px;
    margin-top: 10px;
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
