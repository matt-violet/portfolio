<template>
  <div id='bio-wrapper'>
    <img :src='pic' id='pic'/>
    <div id='titleSection'>
      <h1 class='words'>{{ name }}</h1>
      <h3 class='words'>{{ title }}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: 'About',
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
  #bio-wrapper {
    margin-top: 100px;
    margin-left: auto;
    margin-right: auto;
    width: 250px;
  }
  #pic {
    height: 175px;
    width: 175px;
    border-radius: 50%;
    display: block;
    margin-left: auto;
    margin-right: auto;
  }
  #titleSection {
    text-align: center;
    width: 250px;
    margin-top: 10px;
  }
  .words {
    margin: 0px;
  }
</style>
