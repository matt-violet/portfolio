<template>
  <div>
    <div id="menu-wrapper">
      <div class="menu-option">
        About
      </div>
      <div class="menu-option">
        Portfolio
      </div>
      <div class="menu-option">
        Contact
      </div>
    </div>
    <img :src="image"/>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      image: require('@/images/oakland-sunset.jpg')
    }
  }
}
</script>

<style scoped>
img {
  width: 100%;
  height: 100%;
  opacity: 0.5;
}
#menu-wrapper {
  background-color: lightblue;
  text-align: center;
  height: 40px;
  width: 100%;
}
.menu-option {
  background-color: lightblue;
  display: inline-block;
  vertical-align: middle;
  width: 100px;
  height: 100%;
}
.menu-option:hover {
  background-color: lightcyan;
}
</style>
