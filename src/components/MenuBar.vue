<template>
  <div class="menu-wrapper">
    <div class="centered-menu-div">
      <div class="menu-option">
        <p v-on:click="$emit('onMenuClick', 'about')" class='menu-text' :class="currentPage === 'about' ? 'currentPg' : ''">
          ABOUT
        </p>
      </div>
      <div class="menu-option">
        <p v-on:click="$emit('onMenuClick', 'projects')" class='menu-text' :class="currentPage === 'projects' ? 'currentPg' : ''">
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
      currentPage: 'about',
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
    /* background: white; */
    /* border: 1px solid; */
    position: absolute;
    z-index: 3;
    /* text-align: center; */
    transition: 0.3s all ease-out;
    /* box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.2); */
  }
  .menu-wrapper.menu--hidden {
    transform: translate3d(0, -100%, 0);
  }
  .centered-menu-div {
    /* display: inline-block; */
    margin-left: 15%;
    /* left: 0; */
    /* right: 0; */
    /* padding: 0 5px; */
    /* border-bottom-right-radius: 10px; */
    /* border-bottom-left-radius: 10px; */
  }
  .menu-option {
    animation-duration: 1s;
    display: inline-block;
    margin: 0 24px 0 0;
  }
  .menu-text {
    font-size: 14px;
    height: 100%;
    margin: 0;
  }
  .menu-text:hover {
    cursor: pointer;
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
