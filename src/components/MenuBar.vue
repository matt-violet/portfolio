<template>
  <div class="menu-wrapper">
    <div class="menu-option home-btn">
      <p v-on:click="$emit('onMenuClick', 'home')" v-bind:class="currentPage === 'home' ? 'currentPg' : ''">Home</p>
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
  .menu-wrapper {
    width: 100%;
    height: 80px;
    text-align: center;
    background-color: black;
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
  .home-btn {
    color: white;
    float: left;
    margin-left: 25px;
    display: inline-block;
  }
  .menu-option:hover {
    cursor: pointer;
    transform: scale(1.2);
  }
  .currentPg {
    color: slateblue;
  }
  @keyframes slideRight {
    from { transform: translateX(-900px); }
    to { transform: translateX(0px); }
  }
</style>
