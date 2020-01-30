<template>
  <div id="bg">
  </div>
</template>

<script>
export default {
  name: 'About',
  data() {
    return {
      bgPic: require('../images/matt-taj.jpg')
    }
  }
}
</script>

<style scoped>
  #bg {
    height: 500px;
    width: 500px;
    background-color: green;
    display: block;
    margin-left: auto;
    margin-right: auto;
  }
</style>