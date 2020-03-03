<template type="text/x-template">
  <transition name="modal">
    <div class="modal-mask">
      <a class="modal-close-button" @click="$emit('viewProjectDetails', project)">
        &times;
      </a>
      <div class="modal-wrapper">
        <div v-if="!project.design" class="modal-container">
          <div class="video-div">
            <iframe width="660" height="415" :src="project.video" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
          </div>
          <div class="description-div">
            <h1>{{ project.title }}</h1>
            <p class='details'>{{ project.details }}</p>
            <p class='stack'>{{ project.stack }}</p>
            <a class='github-link' :href="project.github" target="_blank">GitHub Repository</a>
          </div>
        </div>

        <div v-if="project.design" class="modal-container-design">
          <div class="img-div-design">
            <img :src="project.image" class='img-design'/>
          </div>
        </div>

      </div>
    </div>
  </transition>
</template>

<script>
export default {
  name: "ProjectDetails",
  props: {
    project: { type: Object }
  },
  data() {
    return {
      featuredProject: {},
    }
  },
  mounted: {
    setProject: function() {
      this.$data.clickedProject = this.featuredProject;
    }
  }
}
</script>

<style scoped>
  h1 {
    text-align: left;
    margin: 0;
  }
  .details, .stack, .github-link {
    font-size: 16px;
    line-height: normal;
  }
  .github-link:hover {
    cursor: pointer;
  }
  .video-div {
    height: 50%;
    overflow: hidden;
  }
  .description-div {
    padding: 20px 30px;
  }
  .img-div-design {
    max-height: 600px;
    overflow: auto;
  }
  .img {
    width: 100%;
  }
  .img-design {
    vertical-align: bottom;
    width: 100%;
  }
  .modal-mask {
    position: fixed;
    z-index: 9998;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, .8);
    display: table;
    transition: opacity .3s ease;
    text-align: left;
  }
  .modal-wrapper {
    display: table-cell;
    vertical-align: middle;
  }
  .modal-container {
    width: 660px;
    margin: 0px auto;
    background-color: white;
    border-radius: 2px;
    box-shadow: 0 20px 8px rgba(0, 0, 0, .33);
    transition: all .3s ease;
  }
  .modal-container-design {
    width: 800px;
    margin: 0px auto;
    padding: 10px;
    background: white;
    border-radius: 2px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, .33);
    transition: all .3s ease;
    border: 1px solid gray;
  }
  .modal-close-button {
    float: left;
    position: absolute;
    font-size: 80px;
    margin: 40px 80px;
    color: white;
  }
  .modal-close-button:hover {
    cursor: pointer;
  }
</style>