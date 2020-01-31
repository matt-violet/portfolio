<template>
  <div id='home-wrapper'>
    <img :src='pic' id='pic'/>
    <div id='titleSection'>
      <h1 class='words'>{{ name }}</h1>
      <h3 class='words'>{{ title }}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
      pic: require('../images/matt-taj.jpg'),
      title: "Software Engineer",
      name: "Matthew Violet"
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
  #pic {
    height: 200px;
    width: 200px;
    border-radius: 50%;
    border: 1px solid;
    display: block;
    margin-left: auto;
    margin-right: auto;
    animation-duration: 1s;
    animation-name: slideDown;
  }
  #titleSection {
    text-align: center;
    width: 250px;
    margin-top: 10px;
    animation-duration: 1s;
    animation-name: slideUp;
  }
  .words {
    margin: 0px;
  }
  @keyframes slideDown {
    from { transform: translateY(-1200px); }
    to { transform: translateY(0px); }
  }
  @keyframes slideUp {
    from { transform: translateY(1200px); }
    to { transform: translateY(0px); }
  }
</style>
