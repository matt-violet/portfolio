<template>
  <div class="menu-wrapper" id="menu" :class="{ 'menu--hidden': !showMenu }">
    <div class="centered-menu-div">
      <div class="menu-option">
        <p v-on:click="$emit('onMenuClick', 'home')" :class="currentPage === 'home' ? 'currentPg' : ''">
          Home
        </p>
      </div>
      <div class="menu-option">
        <p v-on:click="$emit('onMenuClick', 'about')" :class="currentPage === 'about' ? 'currentPg' : ''">
          About
        </p>
      </div>
      <div class="menu-option">
        <p v-on:click="$emit('onMenuClick', 'portfolio')" :class="currentPage === 'portfolio' ? 'currentPg' : ''">
          Portfolio
        </p>
      </div>
      <div class="menu-option">
        <p v-on:click="$emit('onMenuClick', 'contact')" :class="currentPage === 'contact' ? 'currentPg' : ''">
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
    background: lightblue;
    transition: 0.3s all ease-out;
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
  p {
    line-height: 25px;
    font-size: 18px;
    margin-bottom: 0;
  }
  p:hover {
    cursor: pointer;
    transform: scale(1.1);
  }
  .currentPg {
    border-bottom: 1px solid;
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
