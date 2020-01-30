<template>
  <div id="menu-wrapper">
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
      currentPage: 'home'
    }
  },
  watch: {
    currentPg: function() {
      this.$data.currentPage = this.currentPg
    }
  }
}
</script>

<style>
  #menu-wrapper {
    width: 100%;
    height: 80px;
    text-align: center;
    background-color: black;
  }
  .menu-option {
    animation-duration: 1s;
    animation-name: slideRight;
    color: white;
    display: inline-block;
    width: 100px;
    height: 100%;
  }
  p {
    line-height: 40px;
    font-size: 20px;
  }
  .menu-option:hover {
    color: slateblue;
    cursor: pointer;
  }
  .currentPg {
    color: slateblue;
  }
  @keyframes slideRight {
    from { transform: translateX(-1200px); }
    to { transform: translateX(0px); }
  }
</style>
