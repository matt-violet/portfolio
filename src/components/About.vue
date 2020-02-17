<template>
  <div class="about-component">
    <div class="left-div">
      <div class="about-me">
        <h1 class="about-header">What I Can Do</h1>
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Non, voluptatem. Voluptatum eum error dolorem temporibus qui maxime non, itaque alias explicabo deleniti. Repellat molestiae neque, eligendi optio ab facilis quaerat.
        <ul>
          <li>asdfasdfasdf</li>
          <li>asdfasdfasdf</li>
          <li>asdfasdfasdf</li>
        </ul>
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Non, voluptatem. Voluptatum eum error dolorem temporibus qui maxime non, itaque alias explicabo deleniti. Repellat molestiae neque, eligendi optio ab facilis quaerat.
      </div>
    </div>
    <div class="right-div">
      <div class='box-div'>
        <div class="col">
          <h2 class="skill-header">Software</h2>
          <ul class="bullets">
            <li>5 months as software internship</li>
            <li>Bootcamp graduate</li>
            <li>Driven to self teach</li>
          </ul>
        </div>
        <div class="col">
          <h2 class="skill-header">Design</h2>
          <ul class="bullets">
            <li>3+ years hands on experience</li>
            <li>Photoshop, InDesign, Sketchable</li>
          </ul>
        </div>
         <div class="col">
          <h2 class="skill-header">Video</h2>
          <ul class="bullets">
            <li>3+ years hands on experience</li>
            <li>iMovie</li>
          </ul>
        </div>
      </div>
    </div>
  </div>  
</template>

<script>
export default {
  name: 'about',
}
</script>

<style>
  .about-component {
    width: 100%;
    background: darkseagreen;
  }
  .left-div {
    width: 50%;
    display: inline-block;
    position: relative;
  }
  .right-div {
    display: inline-block;
    position: absolute;
    padding: 100px 60px;
  }
  .about-me {
    padding: 100px 60px;
    width: 500px;
    float: right;
  }
  .about-header {
    margin-top: 0;
    font-size: 40px;
    color: white;
  }
  .box-div {
    margin: 0 auto;
    width: 500px;
  }
  .col {
    padding: 10px;
    width: 29%;
    font-size: 13px;
    vertical-align: top;
    display: inline-block;
  }
  .skill-header {
    font-size: 25px;
    margin-top: 0;
    color: white;
  }
  .bullets {
    padding: 0;
  }
</style>