<template>
  <div>
    <div id="menu-wrapper">
      <div class="menu-option">
        <p>
        About
        </p>
      </div>
      <div class="menu-option">
        <p>
        Portfolio
        </p>
      </div>
      <div class="menu-option">
        <p>
        Contact
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MenuBar'
}
</script>

<style>
  #menu-wrapper {
    text-align: center;
    width: 100%;
  }
  .menu-option {
    display: inline-block;
    vertical-align: middle;
    width: 100px;
    height: 100%;
  }
  p {
    vertical-align: middle;
  }
  .menu-option:hover {
    color: white;
  }
</style>
