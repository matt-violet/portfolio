<template>
  <div class="menu-wrapper" id="menu" :class="{ 'menu--hidden': !showMenu }">
    <div class="centered-menu-div">
      <div class="menu-option">
        <p v-on:click="$emit('onMenuClick', 'home')" class='menu-text' :class="currentPage === 'home' ? 'currentPg' : ''">
          HOME
        </p>
      </div>
      <div class="menu-option">
        <p v-on:click="$emit('onMenuClick', 'about')" class='menu-text' :class="currentPage === 'about' ? 'currentPg' : ''">
          ABOUT
        </p>
      </div>
      <div class="menu-option">
        <p v-on:click="$emit('onMenuClick', 'portfolio')" class='menu-text' :class="currentPage === 'projects' ? 'currentPg' : ''">
          PROJECTS
        </p>
      </div>
      <div class="menu-option">
        <p v-on:click="$emit('onMenuClick', 'contact')" class='menu-text' :class="currentPage === 'contact' ? 'currentPg' : ''">
          CONTACT
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MenuBar',
  props: {
    onMenuClick: { type: Function },
    currentPg: { type: String }
  },
  data() {
    return {
      currentPage: 'home',
      showMenu: true,
      lastScrollPosition: 0
    }
  },
  watch: {
    currentPg: function() {
      this.$data.currentPage = this.currentPg
    }
  },
  mounted () {
    window.addEventListener('scroll', this.onScroll)
  },
  methods: {
    onScroll () {
      const currentScrollPosition = window.pageYOffset || document.documentElement.scrollTop;
      if (currentScrollPosition < 0) {
        return;
      }
      if (Math.abs(currentScrollPosition - this.lastScrollPosition) < 60) {
        return;
      }
      this.showMenu = currentScrollPosition < this.lastScrollPosition;
      this.lastScrollPosition = currentScrollPosition;
    }
  }
}
</script>

<style>
  .menu-wrapper {
    min-width: 600px;
    height: 60px;
    position: absolute;
    text-align: center;
    color: rgb(179, 179, 179);
    background: rgb(53, 53, 53);
    border-bottom: 1px solid black;
    transition: 0.3s all ease-out;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.2);
    animation-duration: .75s;
    animation-name: slideDown;
  }
  .menu-wrapper.menu--hidden {
    transform: translate3d(0, -100%, 0);
  }
  .centered-menu-div {
    width: 500px;
    height: 100%;
    display: inline-block;
    margin-left: auto;
    margin-right: auto;
    left: 0;
    right: 0;
  }
  .menu-option {
    animation-duration: 1s;
    display: inline-block;
    height: 100%;
    margin-left: 25px;
    margin-right: 25px;
  }
  .menu-text {
    font-size: 18px;
    margin-bottom: 0;
  }
  .menu-text:hover {
    cursor: pointer;
    color: white;
    /* transform: scale(1.1); */
  }
  .currentPg {
    /* border-bottom: 1px solid; */
    color: white;
  }
  @keyframes slideDown {
    from { transform: translateY(-90px); }
    to { transform: translateX(0px); }
  }
</style>
