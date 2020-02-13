<template>
  <div class="menu-wrapper" id="menu" :class="{ 'menu--hidden': !showMenu }">
    <div class="centered-menu-div">
      <div class="menu-option">
        <p v-on:click="$emit('onMenuClick', 'home')" v-bind:class="currentPage === 'home' ? 'currentPg' : ''">
          Home
        </p>
      </div>
      <div class="menu-option">
        <p v-on:click="$emit('onMenuClick', 'about')" v-bind:class="currentPage === 'about' ? 'currentPg' : ''">
          About
        </p>
      </div>
      <div class="menu-option">
        <p v-on:click="$emit('onMenuClick', 'portfolio')" v-bind:class="currentPage === 'portfolio' ? 'currentPg' : ''">
          Portfolio
        </p>
      </div>
      <div class="menu-option">
        <p v-on:click="$emit('onMenuClick', 'contact')" v-bind:class="currentPage === 'contact' ? 'currentPg' : ''">
          Contact
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
  // beforeDestroy () {
  //   window.removeEventListener('scroll', this.onScroll)
  // },
  methods: {
    onScroll () {
      const currentScrollPosition = window.pageYOffset || document.documentElement.scrollTop;
      if (currentScrollPosition < 0) {
        return;
      }
      // Stop executing this function if the difference between
      // current scroll position and last scroll position is less than some offset
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
    height: 70px;
    position: absolute;
    text-align: center;
    background-color: black;
    border-bottom: 1px solid;
    transition: 0.3s all ease-out;
  }
  .menu-wrapper.menu--hidden {
    transform: translate3d(0, -100%, 0);
  }
  .centered-menu-div {
    width: 500px;
    display: inline-block;
    margin-left: auto;
    margin-right: auto;
    left: 0;
    right: 0;
  }
  .menu-option {
    animation-duration: 1s;
    color: white;
    display: inline-block;
    height: 100%;
    padding-left: 25px;
    padding-right: 25px;
  }
  p {
    line-height: 40px;
    font-size: 20px;
  }
  .menu-option:hover {
    cursor: pointer;
    transform: scale(1.2);
  }
  .currentPg {
    color: rgb(131, 131, 255);
  }
  .home-icon {
    width: 40px;
    border: 1px solid;
    vertical-align: middle
  }
  @keyframes slideRight {
    from { transform: translateX(-900px); }
    to { transform: translateX(0px); }
  }
</style>
