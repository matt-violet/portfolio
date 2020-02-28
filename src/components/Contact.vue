<template>
  <div class="contact-component" id="contact">
    <div class="contact-banner">
      <div class="left animatedParent">
        <img src="../images/matt-violet.png" class="left-side-img animated slideInLeft">
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
      <div class=contact-links>
        <a class='link-text' href=''>Email</a>
        <a class='link-text' href='githubLink'>GitHub</a>
        <a class='link-text' href='linkedinLink'>LinkedIn</a>
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
  .contact-component {
    position: absolute;
    padding-top: 52px;
    width: 100%;
    background-image: linear-gradient(to right, #eea2a2 0%, #bbc1bf 19%, #57c6e1 42%, #b49fda 79%, #7ac5d8 100%);
  }
  .contact-banner {
    height: 400px;
    text-align: center;
  }
  .left {
    width: 50%;
    height: 400px;
    display: inline-block;
    position: relative;
    text-align: center;
  }
  .right {
    width: 50%;
    height: 400px;
    display: inline-block;
    z-index: 2;
    overflow: hidden;
  }
  .left-side-img {
    height: 85%;
    margin: auto;
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
    margin-top: 250px;
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