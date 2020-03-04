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
    <div class="contact-component">
      <h2 class='contact-header' data-aos="zoom-in" data-aos-delay='500'>Contact</h2>
      <div class='contact-btns' data-aos="zoom-in" data-aos-delay='600'>
        <div class="contact-btn" v-on:click='onLinkClick("mattviolet@gmail.com")'>
          <span class='helper'></span>
          <img src='../images/mail-icon.png' class='contact-icon'>
        </div>
        <div class="contact-btn" v-on:click='onLinkClick(github)'>
          <span class='helper'></span>
          <img src='../images/github-icon.png' class='contact-icon'>
        </div>
        <div class="contact-btn" v-on:click='onLinkClick(linkedin)'>
          <span class='helper'></span>
          <img src='../images/linkedin-icon.png' class='contact-icon'>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Contact',
  data() {
    return {
      github: 'https://github.com/matt-violet',
      linkedin: 'https://www.linkedin.com/in/mattviolet/',
    }
  },
  methods: {
    onLinkClick(url) {
      if (url === 'mattviolet@gmail.com') {
        window.location.href = "mailto:" + url;
      } else {
        window.open(url, '_blank');
      }
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
    height: 300px;
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
    height: 85%;
    margin-right: 80px;
    position: absolute;
    bottom: 0;
    right: 0;
    z-index: 1;
  }
  .right-side-text {
    width: 400px;
    color: rgb(43, 43, 43);
    text-align: left;
  }
  .contact-header {
    margin: 20px auto 40px auto;
    text-align: center;
    font-size: 25px;
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
  .contact-btns {
    width: 400px;
    height: 75px;
    text-align: center;
    margin: 40px auto;
  }
  .contact-btn {
    background: linear-gradient(135deg, #e3ffe7 0%, #d9e7ff 100%);
    display: inline-block;
    margin: 0 20px;
    text-align: center;
    vertical-align: middle;
    width: 70px;
    height: 70px;
    border-radius: 50%;
    border: 1px solid gray;
  }
  .contact-btn:hover {
    background: linear-gradient(135deg, #00C9FF 0%, #92FE9D 100%);
    cursor: pointer;
  }
  .helper {
    display: inline-block;
    height: 100%;
    vertical-align: middle;
  }
  .link {
    background: red;
    width: 100%;
    height: 100%;
    border-radius: 50%;
  }
  .contact-icon {
    width: 35px;
    height: 35px;
    vertical-align: middle;
  }
  .email-link .email-tool-tip {
    visibility: hidden;
    background-color: black; opacity: .8;
    border-radius: 10%;
    border: 1px solid white;
    color: white;
    position: absolute;
  }
  .email-link:hover .email-tool-tip {
    visibility: visible;
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