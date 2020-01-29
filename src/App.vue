<template>
  <div id="app">
    <MenuBar/>
    <About/>
  </div>
</template>

<script>
import About from './components/About.vue'
import MenuBar from './components/MenuBar.vue'

export default {
  name: 'app',
  components: {
    MenuBar,
    About
  }
}
</script>

<style>
  body {
    background-image: url('./images/oakland-sunset.jpg');
    background-position: center top;
  }
</style>
