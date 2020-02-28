<template>
  <div class="about-component" id="about">
    <h1 class='about-header'>About Me</h1>
    <div class="about-me">
      <p class='bio-text'>
        Native of Oakland, CA, I have a big heart and I bring passion to everything I do. I dedicated the first chapter of my career to non-profit marketing / communications work, supporting various communities both at home and abroad.
      </p>
      <p class='bio-text'>
        My interest in software came in 2015, at a time of major change in my life. Shortly after I was diagnosed with type one diabetes, I started wearing two electronic medical devices that worked together to create a hybrid closed-loop system to help manage my blood sugar levels. As someone whose health is now literally tied to automated algorithms, my appreciation for the power of code has changed forever.
      </p>
      <p class='bio-text'>
        Understanding what technological innovation has done for me, and can do for others, is what motivates me to dream big, learn new things, and tackle complex problems. 
      </p>
      <div class='about-imgs'>
        <img src='../images/matt-guitar.jpg' class='about-img'>
        <img src='../images/maesot.jpg' class='about-img'>
        <img src='../images/matt-cgm.jpg' class='about-img'>
        <img src='../images/matt-dubs.jpg' class='about-img'>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'about'
}
</script>

<style>
  .about-component {
    background: white;
    width: 60%;
    margin: 80px auto;
    color: rgb(43, 43, 43);
    border-bottom: 1px solid gray;
  }
  .about-imgs {
    width: 100%;
    text-align: center;
    margin: 40px 0;
  }
  .about-img {
    width: 25%;
    display: inline-block;
  }
  .about-me {
    padding: 0px 15%;
    margin-bottom: 80px;
    height: 100%;
  }
  .about-header {
    margin: 0 auto;
    padding-bottom: 40px;
    text-align: center;
    color: rgb(43, 43, 43);
    font-size: 40px;
  }
  .bio-text {
    margin-bottom: 10px;
    font-size: 14px;
    display: inline-block;
  }
</style>