<template>
  <div id="menu-wrapper">
    <div class="menu-option">
      <p v-on:click="$emit('menuClick', 'home')">
        Home
      </p>
    </div>
    <div class="menu-option">
      <p v-on:click="$emit('menuClick', 'about')">
        About
      </p>
    </div>
    <div class="menu-option">
      <p v-on:click="$emit('menuClick', 'portfolio')">
        Portfolio
      </p>
    </div>
    <div class="menu-option">
      <p v-on:click="$emit('menuClick', 'contact')">
        Contact
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MenuBar',
  props: {
    menuClick: { type: Function },
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
  @keyframes slideRight {
    from { transform: translateX(-1200px); }
    to { transform: translateX(0px); }
  }
</style>
