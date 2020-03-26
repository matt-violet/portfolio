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
    width: 636px;
    margin: 0 auto;
  }
  .header {
    margin-left: 20px;
  }
  .project {
    width: 295px;
    margin: 10px;
    border: 1px solid gray;
    display: inline-block;
    text-align: center;
  }
  .project:hover {
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.4), 0 6px 20px 0 rgba(0, 0, 0, 0.4);
  }
  .project-title {
    margin: 0 0 5px 0;
  }
  /* ------------------------------ DIMMER EFFECT ------------------------------- */
  .dimmer {
    background: rgba(255, 255, 255, 0.75);
    height: 265px;
    width: 295px;
    position: absolute;
    display: none;
    z-index: 1;
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
    padding: 7px;
    font-size: 12px;
    border: 1px solid;
    animation: pulse 1.5s infinite;
  }
  .details-btn:hover {
    cursor: pointer;
    color: white;
    background: rgb(82, 82, 82);
  }
  @keyframes pulse
  {
    50% {
      transform: scale(1.1);
    }
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
  @media (max-width: 700px) {
    .project {
      display: block;
      margin: 0 auto 20px auto;
    }
    .outer-wrapper {
      width: 100%;
    }
  }
</style>