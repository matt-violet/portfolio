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
    width: 100%;
    position: fixed;
    z-index: 3;
    text-align: center;
    color: rgb(43, 43, 43);
    background: white; opacity: .95;
    transition: 0.3s all ease-out;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.2);
  }
  .menu-wrapper.menu--hidden {
    transform: translate3d(0, -100%, 0);
  }
  .centered-menu-div {
    display: inline-block;
    left: 0;
    right: 0;
  }
  .menu-option {
    animation-duration: 1s;
    display: inline-block;
    margin: 0 15px;
  }
  .menu-text {
    font-size: 16px;
    height: 100%;
  }
  .menu-text:hover {
    cursor: pointer;
    color: coral;
  }
  .currentPg {
    color: coral;
  }
  @keyframes slideDown {
    from { transform: translateY(-90px); }
    to { transform: translateX(0px); }
  }
</style>
