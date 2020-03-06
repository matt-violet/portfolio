<template type="text/x-template">
  <transition name="modal">
    <div class="modal-mask">
      <a class="modal-close-button" @click="$emit('viewProjectDetails', project)">
        &times;
      </a>
      <div v-if="!project.design" class="modal-wrapper">
        <div class="modal-container">
          <div class="video-div">
            <iframe v-if='project.id!==4' class="video" max-width="100%" height="100%" :src="project.video" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
            <img v-else class='socialInnPic' width="660" height="415" :src='project.video'>
            <!-- <img v-else :src='project.video'> -->
          </div>
          <div class="description-div">
            <h1>{{ project.title }}</h1>
            <p class='details'>{{ project.details }}</p>
            <p class='stack'>{{ project.stack }}</p>
            <a class='github-link' :href="project.github" target="_blank">GitHub Repository</a>
          </div>
        </div>
      </div>
      <div v-else class="modal-wrapper-design">
        <div class="modal-container-design">
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
    viewProjectDetails: { type: Function },
    project: { type: Object },
  },
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
    height: 60%;
    text-align: center;
    overflow: hidden;
  }
  .video {
    width: 100%;
    height: 100%;
  }
  .img {
    width: 100%;
  }
  .socialInnPic {
    max-height: 100%;
    max-width: 100%;
  }
  .description-div {
    padding: 20px 30px;
  }
  .modal-mask {
    position: fixed;
    z-index: 9998;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, .9);
    display: table;
    transition: opacity .3s ease;
    text-align: left;
    vertical-align: middle;
  }
  .modal-wrapper {
    display: table-cell;
    margin: auto;
    padding: 10px 0;
    vertical-align: middle;
  }
  .modal-container {
    width: 50%;
    height: 80%;
    overflow: auto;
    margin: auto;
    border: 1px solid white;
    background-color: white;
    transition: all .3s ease;
  }
  .modal-wrapper-design {
    display: table-cell;
    margin: auto;
    padding: 10px 0;
    vertical-align: middle;
  }
  .modal-container-design {
    width: 50%;
    height: 80%;
    overflow: auto;
    margin: auto;
    padding: 5px;
    /* background-color: white; */
    transition: all .3s ease;
  }
  .img-div-design {
    height: 100%;
    overflow: auto;
    vertical-align: middle;
  }
  .img-design {
    width: 100%;
  }
  .modal-close-button {
    float: left;
    position: absolute;
    font-size: 80px;
    margin: 0px 40px;
    color: white;
  }
  .modal-close-button:hover {
    cursor: pointer;
  }
</style>