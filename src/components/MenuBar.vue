<template>
  <div class="menu-wrapper">
    <div class="centered-menu-div">
      <div class="menu-option">
        <p v-on:click="$emit('onMenuClick', 'projects')" class='menu-text' :class="currentPage === 'projects' ? 'currentPg' : ''">
          WORK
        </p>
      </div>
      <div class="menu-option">
        <p v-on:click="$emit('onMenuClick', 'about')" class='menu-text' :class="currentPage === 'about' ? 'currentPg' : ''">
          ABOUT
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
      currentPage: 'projects',
      showMenu: true,
      lastScrollPosition: 0,
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
    margin-top: 30px;
    background: hsl(0, 0%, 100%, 0);
    position: absolute;
    z-index: 3;
    transition: 0.3s all ease-out;
  }
  .menu-wrapper.menu--hidden {
    transform: translate3d(0, -100%, 0);
  }
  .centered-menu-div {
    margin-left: 15%;
  }
  .menu-option {
    animation-duration: 1s;
    display: inline-block;
    margin: 0 28px 0 0;
  }
  .menu-text {
    font-size: 13px;
    font-weight: 400;
    height: 100%;
    margin: 0;
    transition: all .2s ease-in-out;
  }
  .menu-text:hover {
    cursor: pointer;
  }
  .currentPg {
    color: white;
  }
  @keyframes slideDown {
    from { transform: translateY(-90px); }
    to { transform: translateX(0px); }
  }
</style>
