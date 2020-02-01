<template>
  <div class="contact-wrapper">
    <div class='centered'>
      <p>{{ email }}</p>
      <p>
        <i class="devicon-github-plain colored"></i>
        {{ github }}
      </p>
      <p>{{ linkedin }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Contact',
  data() {
    return {
      email: 'mattviolet@gmail.com',
      github: 'https://github.com/matt-violet',
      linkedin: 'https://www.linkedin.com/in/mattviolet/'
    }
  }
}
</script>

<style scoped>
  p {
    font-size: 14px;
    line-height: normal;
  }
  .contact-wrapper {
    margin-top: 150px;
    position: fixed;
    width: 100%;
  }
  .centered {
    width: 250px;
    margin-left: auto;
    margin-right: auto;
  }
</style>