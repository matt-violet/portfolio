<template>
  <div class="outer-wrapper">
    <div
      v-for="project of projects" 
      v-on:click="$emit('viewProjectDetails', project)"
      v-bind:key="project.id"
      class="project"
    >
      <div class="img-div">
        <img :src="project.image" class='img'/>
      </div>
      <h2>{{ project.title }}</h2>
      <p>{{ project.description }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SoftwareProjects',
  props: {
    viewProjectDetails: { type: Function },
    softwareProjects: { type: Array },
  },
  data() {
    return {
      projects: []
    }
  },
  mounted() {
    this.$data.projects = this.softwareProjects
  },
}
</script>

<style scoped>
  h2 {
    margin: 5px 0px 5px 0px;
    color: black;
  }
  p {
    font-size: 14px;
    line-height: normal;
    color: black;
    margin: 0;
  }
  .header {
    margin-left: 20px;
  }
  .projects-header {
    animation-duration: .75s;
    animation-name: slideDown;
  }
  .project {
    width: 300px;
    background-color: white;
    margin: 20px;
    padding: 10px;
    display: inline-block;
    animation-duration: .75s;
    animation-name: slideLeft;
  }
  .project:hover {
    -webkit-transform: scale(1.01);
    -ms-transform: scale(1.05);
    transform: scale(1.05);
    cursor: pointer;
  }
  .img-div {
    width: 100%;
    height: 150px;
    overflow: hidden;
  }
  .img {
    width: 100%;
    height: auto;
  }
  @keyframes slideDown {
    from { transform: translateY(-500px); }
    to { transform: translateY(0px); }
  }
  @keyframes slideLeft {
    from { transform: translateX(1000px); }
    to { transform: translateX(0px); }
  }
</style>