<template>
  <div class="home-component" id="home">
    <div class='home-wrapper'>
      <table class='table'>
        <tr>
          <td>
            <h1 class='line1'>Matt Violet</h1>
            <h1 class='line2'>Software engineer</h1>
            <h1 class='line3'>Oakland, CA</h1>
            <img src="../images/down-arrow.png"
              class="down-arrow"
              onClick="document.getElementById('about').scrollIntoView({ behavior: 'smooth' })"
            />
          </td>
          <td>
            <img class='photo' src='../images/matt-violet.png'/>
          </td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
}
</script>

<style>
  .home-wrapper {
    width: 100%;
    position: absolute;
  }
  .table {
    width: 50%;
    margin: 0px auto;
    line-height: normal;
  }
  .line1 {
    font-size: 50px;
  }
  .line2, .line3 {
    font-size: 20px;
    line-height: 15px;
  }
  .photo {
    height: 300px;
    width: 300px;
    border-radius: 50%;
    border: 1px solid;
    background-color: white;
  }
  .down-arrow {
    display: block;
    margin: 70px auto 0px auto;
    height: 20px;
  }
  .down-arrow:hover {
    cursor: pointer;
    transform: scale(1.2);
  }
</style>
