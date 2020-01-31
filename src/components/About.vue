<template>
  <div class="about-wrapper">
    <div class="leftt outer">
      <div class="inner-left">
        <img :src="aboutPic" class="aboutPic"/>
      </div>
    </div>
    <div class="rightt outer">
      <div class="inner-right">
        <h1>about me</h1>
        <p>
          Software Engineer with a background in marketing/communications and graphic design. My experience includes building/maintaining full stack web applications through agile workflow, test driven development, and continuous integration.
          <br><br>
          My passion for software engineering comes from the role technological innovation plays in my own life, as someone who uses an insulin pump integrated with continuous glucose monitoring to manage type one diabetes. I have designed, optimized, and deployed complete systems using technologies such as HTML5, CSS, JavaScript, React, Vue, JQuery, Node.js, Express, MongoDB, PostgreSQL, MySQL, GraphQL, Cassandra, Jest/Enzyme, Mocha/Chai, Webpack, Amazon Web Services, and more. I look forward to building responsive, dynamic applications that make a meaningful difference in people's lives.
          <br><br>
          When not coding I can be found making music, sketching, and hanging out in my hometown of Oakland, CA. Check out my Github at https://github.com/matt-violet or shoot me an email at mattviolet@gmail.com.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'About',
  data() {
    return {
      aboutPic: require('../images/matt-taj.jpg'),
    }
  }
}
</script>

<style scoped>
  h1 {
    font-size: 50px;
    margin: 0;
    text-align: left;
  }
  p {
    font-size: 14px;
    line-height: normal;
  }
  .outer {
    margin-top: 150px;
    height: 100%;
    width: 50%;
    position: fixed;
    z-index: 1;
    bottom: 0;
    overflow-x: hidden;
  }
  .leftt {
    left: 0;
  }
  .rightt {
    right: 0;
  }
  .inner-left {
    bottom: 100px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -80%);
    text-align: left;
    width: 80%;
  }
  .inner-right {
    bottom: 100px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-85%, -85%);
    text-align: left;
  }
  .aboutPic {
    width: 350px;
    float: right;
    border: 1px solid;
    transform: rotate(6deg);
  }
</style>