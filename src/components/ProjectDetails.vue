<template type="text/x-template">
  <transition name="modal">
    <div class="modal-mask">
      <a class="modal-close-button" @click="$emit('viewProjectDetails', project)">
        &times;
      </a>

      <div v-if="!project.design" class="modal-wrapper">
        <div class="modal-container">
          <div class="video-div">
            <iframe v-if='project.title!=="Social Inn" && project.title!=="Segment Events" && project.title!=="Internal Tool"' class="video" max-width="100%" height="100%" :src="project.video" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
            <img v-else class='project-img' width="660" height="415" :src='project.video'>
          </div>
          <div class="description-div">
            <h1 class='project-title'>{{ project.title }}</h1>
            <p class='details'>{{ project.details }}</p>
            <div v-if='project.image2'>
              <img :src='project.image2' class='bolus-math'>
            </div>
            <div  v-if='project.stack' class='stack-div'>
              <p v-for='stack in project.stack' v-bind:key="stack" class='stack'>{{ stack }}</p>
            </div>
            <a v-if='project.github.length !== 2' class='github-link' :href="project.github" target="_blank">GitHub Repository</a>
            <a v-else v-for='link of project.github' v-bind:key="link" class='github-link-2' :href="link.link" target="_blank">{{link.repo}}</a>
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
  .project-title {
    font-size: 28px;
  }
  .stack-div {
    margin-bottom: 10px;
  }
  .stack {
    display: inline-block;
    background: lightgrey;
    border-radius: 10px;
    padding: 5px 10px;
    margin: 5px 5px 5px 0;
  }
  .details, .stack, .github-link {
    font-size: 16px;
    line-height: normal;
  }
  .details, .stack {
    color: grey;
    font-weight: 400;
  }
  .github-link:hover {
    cursor: pointer;
  }
  .github-link-2 {
    display: block;
    margin: 0 0 10px 0;
  }
  .video-div {
    height: 60%;
    text-align: center;
    vertical-align: middle;
    overflow: hidden;
  }
  .video {
    width: 100%;
    height: 100%;
  }
  .img {
    width: 100%;
  }
  .project-img {
    max-height: 100%;
    width: 100%;
  }
  .description-div {
    padding: 20px 40px 40px 40px;
    border-top: 1px solid;
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
    height: 85%;
    overflow: auto;
    margin: auto;
    /* border: 1px solid white; */
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
    font-size: 70px;
    font-weight: 300;
    margin: 0px 40px;
    color: rgb(139, 139, 139);
  }
  .modal-close-button:hover {
    transition: .5s;
    color: white;
    cursor: pointer;
  }
   .bolus-math {
    width: 100%;
  }
  @media (max-width: 1000px) {
    .project-title {
      font-size: 22px;
    }
    .details, .stack, .github-link {
      font-size: 12px;
    }
    .description-div {
      padding: 20px;
    }
  }
</style>