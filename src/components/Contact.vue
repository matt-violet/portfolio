<template>
  <div class="contact-component" id="contact">
    <div class="contact-wrapper">
      <h1>
        Get in Touch
      </h1>
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
  },
  methods: {
    copyText: function() {
      let copyText = document.querySelector("#textarea");
      copyText.select();
      copyText.setSelectionRange(0, 99999)
      document.execCommand("copy");
      alert("Copied the text: " + copyText.name);
    }
  }
}
</script>

<style scoped>
  p {
    font-size: 14px;
    line-height: normal;
  }
  td {
    padding-left: 10px;
    vertical-align: middle;
  }
  .contact-component {
    background: linear-gradient(180deg, hsl(256, 59%, 26%), hsl(248, 55%, 56%));
    color: white;
    padding: 80px 20%;
    height: 200px;
    text-align: center;
  }
  .contact-wrapper {
    height: 100%;
    padding: 20px 40px;
    text-align: center;
  }
  .contact-links {
    margin-top: 80px;
  }
  .textarea {
    color: black;
    display: none;
  }
  .link-text {
    width: 100px;
    height: 200px;
    margin: 0 40px;
    color: white;
  }
  .link-text:visited {
    color: black;
  }
  /* .icon-div {
    width: 30px;
    height: 30px;
    margin: 150px 10px 0 10px;
    vertical-align: middle;
    display: inline-block;
  }
  .icon-div :hover {
    transform: scale(1.05);
    cursor: pointer;
  }
  .icon {
    width: 100%;
  }
  .email {
    width: 35px;
    height: 30px;
  } */
</style>