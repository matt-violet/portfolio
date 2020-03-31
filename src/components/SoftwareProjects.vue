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
          DETAILS
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
    color: grey;
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
    border: 1px solid grey;
    display: inline-block;
    text-align: center;
    border-radius: 10px;
    overflow: hidden;
    transition: all .2s ease-in-out;
  }
  .project:hover {
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.4), 0 6px 20px 0 rgba(0, 0, 0, 0.4);
  }
  .project-title {
    margin: 0 0 5px 0;
  }
  /* ------------------------------ DIMMER EFFECT ------------------------------- */
  .dimmer {
    background: rgba(255, 255, 255, 0.9);
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
    border-top: 1px solid grey;
  }
  .details-btn {
    margin: 15px 0 5px 0;
    padding: 7px 10px;
    font-size: 12px;
    font-weight: 600;
    color: darkslategrey;
    background: rgb(225, 225, 225);
    border-radius: 5px;
    animation: pulse 1.7s infinite;
    transition: all .3s;
  }
  .details-btn:hover {
    cursor: pointer;
    background: darkslategrey;
    color: lightgrey;
  }
  @keyframes pulse
  {
    50% {
      transform: scale(1.15);
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