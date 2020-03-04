<template>
  <div id="app">
    <MenuBar class="menu" @onMenuClick="onMenuClick" :currentPg="currentPg"/>
    <div class="components">
      <About v-if="about"/>
      <Projects v-if="projects"/>
      <Contact v-if="contact"/>
    </div> 
  </div>
</template>

<script>
import MenuBar from './components/MenuBar.vue'
import About from './components/About.vue'
import Projects from './components/Projects.vue'
import Contact from './components/Contact.vue'

export default {
  name: 'app',
  components: {
    MenuBar,
    About,
    Projects,
    Contact,
  },
  data() {
    return {
      currentPg: '',
      about: true,
      projects: false,
      contact: false,
    }
  },
  methods: {
    onMenuClick(option) {
      this.home = false;
      this.about = false;
      this.projects = false;
      this.contact = false;
      this[option] = true;
      this.currentPg = option;
    }
  }
}
</script>

<style>
  body, html {
    min-height: 100%;
    margin: 0;
    font-family: 'IBM Plex Sans', 'Montserrat', sans-serif;
  }
  a {
    color: rgb(43, 43, 43);
  }
</style>
