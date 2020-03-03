<template>
  <div class="contact-wrapper">

    <div class="contact-banner">
      <div class="left animatedParent">
        <img src="../images/matt-look.png" class="left-side-img animated slideInUp">
      </div>
      <div class="right animatedParent">
        <div class="right-side-text animated slideInDown">
          <h1 class="contact-text">
            Need a developer?
          </h1>
          <p class="contact-text-2">
            I can help.
          </p>
        </div>
      </div>
    </div>

    <div class="contact-component animatedParent">
      <h2 class='contact-header'>Contact</h2>
      <div class='contact-links animated pulse'>
        <a class='link-text' href="mailto:mattviolet@gmail.com" target="_top">Email</a>
        <a class='link-text' href='https://github.com/matt-violet' target="blank">GitHub</a>
        <a class='link-text' href='https://linkedin.com/in/mattviolet/' target="blank">LinkedIn</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Contact',
  data() {
    return {
      emailIcon: require('../images/mail-icon.png'),
      emailAddress: 'mattviolet@gmail.com',
      githubLink: 'https://github.com/matt-violet',
      linkedinLink: 'https://linkedin.com/in/mattviolet/',
      linkedinIcon: require('../images/linkedin-icon.png'),
    }
  }
}
</script>

<style scoped>
  .contact-wrapper {
    background: linear-gradient(to left, #b3ffab 0%, #12fff7 100%);
    background-repeat: no-repeat;
    height: 100%;
    padding-bottom: 100px;
  }
  .contact-component {
    padding-top: 40px;
    width: 1000px;
    height: 500px;
    margin: auto;
    border-radius: 20px;
    background: white;
    border: 1px solid;
    position: relative;
    z-index: 2;
    vertical-align: middle;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.4), 0 6px 20px 0 rgba(0, 0, 0, 0.4);
  }
  .contact-banner {
    padding-top: 52px;
    height: 400px;
    width: 100%;
    text-align: center;
    background-image: linear-gradient(to left, #b3ffab 0%, #12fff7 100%);
  }
  .left {
    width: 45%;
    height: 400px;
    display: inline-block;
    position: relative;
    text-align: center;
  }
  .right {
    width: 55%;
    height: 400px;
    position: relative;
    display: inline-block;
    overflow: hidden;
  }
  .left-side-img {
    height: 75%;
    margin-right: 80px;
    position: absolute;
    bottom: 0;
    right: 0;
    z-index: 1;
    /* -webkit-filter: drop-shadow(-8px -4px 8px #222);
    filter: drop-shadow(-8px -4px 8px #222); */
  }
  .right-side-text {
    width: 400px;
    color: rgb(43, 43, 43);
    text-align: left;
  }
  .contact-header {
    margin: 20px auto 40px auto;
    text-align: center;
  }
  .contact-text {
    font-size: 50px;
    margin: 0;
    width: 500px;
  }
  .contact-text-2 {
    margin: 0;
    font-size: 26px;
  }
  .contact-links {
    text-align: center; 
  }
  .link-text {
    margin: 0 20px;
  }
  @keyframes gradient {
    0% {
      background-position: 0% 50%;
    }
    50% {
      background-position: 100% 50%;
    }
    100% {
      background-position: 0% 50%;
    }
  }
</style>