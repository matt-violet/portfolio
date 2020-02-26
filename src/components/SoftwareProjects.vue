<template>
  <div class="outer-wrapper">
    <div
      v-for="project of projects"
      v-bind:key="project.id"
      class="project"
    >
      <div class="img-div">
        <img :src="project.image" class='img'/>
      </div>
      <div class="project-description">
        <h2>{{ project.title }}</h2>
        <p>{{ project.description }}</p>
        <button class='details-btn' v-on:click="$emit('viewProjectDetails', project)">
          View Details
        </button>
      </div>
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
    margin: 0;
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
  .project {
    width: 300px;
    background-color: white;
    margin: 20px;
    display: inline-block;
    text-align: center;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.4), 0 6px 20px 0 rgba(0, 0, 0, 0.4);
  }
  .project-description {
    padding: 10px;
  }
  .details-btn {
    margin: 15px 0 0 0;
    padding: 5px;
    font-size: 12px;
    border: 2px solid;
  }
  .details-btn:hover {
    cursor: pointer;
    transform: scale(1.1);
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
</style>