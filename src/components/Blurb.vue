<template>
  <div class="blurb-component">
    <div class='blurb-div'>
      <img src='../images/matt-violet.png' class='blurb-photo'>
      <div class=bubble>
        <h1 class='hello'>Hi, I'm Matt.</h1>
        <h3 class='blurb'>What can I help you with?</h3>
      </div>
    </div>
    <!-- <img src="../images/down-arrow.png"
      class="down-arrow"
      onClick="document.getElementById('portfolio').scrollIntoView({ behavior: 'smooth' })"
    /> -->
  </div>
</template>

<script>
export default {
  name: 'Blurb',
}
</script>

<style scoped>
  h1 {
    font-size: 50px;
    margin: 0;
    text-align: left;
  }
  .blurb-component {
    width: 100%;
    height: 0px;
    position: absolute;
    z-index: 1;
  }
  .blurb-div {
    width: 330px;
    margin: -60px auto 0 150px;
    position: relative;
  }
  .bubble {
    width: 100%;
    height: 80px;
    padding: 20px 0;
    margin: -20px 0 0 15px;
    text-align: center;
    border-radius: 50%;
    border: 1px solid black;
    background: white;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.4), 0 6px 20px 0 rgba(0, 0, 0, 0.4);
  }
  .blurb-photo {
    z-index: -1;
    width: 100%;
    position: absolute;
    margin: -265px 0 0 15px;
    -webkit-filter: drop-shadow(8px 5px 6px #222);
    filter: drop-shadow(8px 5px 6px #222); 
  }
  .hello {
    font-size: 30px;
    text-align: center;
    margin-bottom: 5px;
    color: black;
  }
  .blurb {
    margin: 0;
    color: black;
  }
  /* -------------------- DOWN ARROW -------------------------- */
  /* .down-arrow {
    display: block;
    margin: 70px auto 0px auto;
    height: 20px;
  }
  .down-arrow:hover {
    cursor: pointer;
    transform: scale(1.2);
  } */
</style>