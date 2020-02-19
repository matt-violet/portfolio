<template>
  <div>
    <div class="about-component" id="about">
      <div class="about-me">
        <h1 class='about-header'>About Me</h1>
        <p class='bio-text'>
          Native of Oakland, CA, I have a big heart and I bring passion to everything I do. I dedicated the first chapter of my career to non-profit marketing / communications work, supporting various communities both at home and abroad.
        </p>
        <p class='bio-text'>
          My interest in software came in 2015, at a time of major change in my life. Shortly after I was diagnosed with type one diabetes, I started wearing two electronic medical devices that worked together to create a hybrid closed-loop system to help manage my blood sugar levels. As someone whose health is now literally tied to automated algorithms, my appreciation for the power of code has changed forever.
        </p>
        <p class='bio-text'>
          Understanding what technological innovation has done for me, and can do for others, is what motivates me to dream big, learn new things, and tackle complex problems. 
        </p>
      </div>
    </div>  
    <Skills/>
  </div>
</template>

<script>
import Skills from './Skills.vue'
export default {
  name: 'about',
  components: {
    Skills,
  }
}
</script>

<style>
  .about-component {
    padding: 80px 160px;
    border-top: 1px solid black;
    background: rgb(236, 236, 236);
  }
  .about-me {
    height: 100%;
    padding: 20px 40px;
    background: white;
  }
  .about-header {
    color: black;
    margin: 0 auto 20px auto;
    padding: 0 0 5px 0;
    text-align: center;
    width: 200px;
    border-bottom: 1px solid;
  }
  .bio-text {
    margin-bottom: 10px;
    font-size: 14px;
    display: inline-block;
    color: rgb(143, 143, 143);
  }
</style>