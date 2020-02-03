<template>
  <div class="contact-wrapper">
    <p>{{ email }}</p>
    <p>
      <i class="devicon-github-plain colored"></i>
      {{ github }}
    </p>
    <p>{{ linkedin }}</p>
    <a href = "mailto: abc@example.com">Send Email</a>
    <form>
      <label>Name</label>
      <input type="text">
    </form>
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
    margin-top: 125px;
    margin-left: auto;
    margin-right: auto;
    left: 0;
    right: 0;
    position: absolute;
    width: 300px;
  }
</style>