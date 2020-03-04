<template>
  <div class="outer-wrapper animatedParent">
    <div v-for="project of projects" v-bind:key="project.id" class="project animated pulse">
      <div class='dimmer animated fadeIn'/>
      <div class="img-div">
        <img :src="project.image" class='img'/>
      </div>
      <div class="project-description">
        <h3 class="project-title">{{ project.title }}</h3>
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
    color: rgb(43, 43, 43);
  }
  p {
    font-size: 14px;
    line-height: normal;
    color: rgb(43, 43, 43);
    margin: 0;
  }
  .outer-wrapper {
    width: 680px;
    margin: 0 auto;
  }
  .header {
    margin-left: 20px;
  }
  .project {
    width: 298px;
    margin: 20px;
    display: inline-block;
    text-align: center;
    border: 1px solid black;
  }
  .project:hover {
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.4), 0 6px 20px 0 rgba(0, 0, 0, 0.4);
  }
  .project-title {
    margin: 0 0 5px 0;
  }
  /* ------------------------------ DIMMER EFFECT ------------------------------- */
  .dimmer {
    background: rgba(61, 61, 61, 0.6);
    height: 262px;
    width: 300px;
    position: absolute;
    display: none;
  }
  div.outer-wrapper div.project:hover div.dimmer {
    display: none;
  }
  div.outer-wrapper:hover div.dimmer {
    display: block;
  }
  /* ---------------------------------------------------------------------------- */
  .project-description {
    padding: 10px;
    background: white;
  }
  .details-btn {
    margin: 15px 0 0 0;
    padding: 5px;
    font-size: 12px;
    border: 1.5px solid;
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