<template type="text/x-template" id="modal-template">
  <transition name="modal">
    <div class="modal-mask">
      <div class="modal-wrapper">

        <div v-if="!project.design" class="modal-container">
          <a class="modal-close-button" @click="$emit('viewProjectDetails')">
            &times;
          </a>
          <div class="img-div">
            <img :src="project.image" class='img'/>
          </div>
          <div class="modal-header">
            <h1>{{ project.title }}</h1>
          </div>
          <div class="modal-body">
            <p>{{ project.details }}</p>
          </div>
          <div class="modal-footer">
            <p>{{ project.stack }}</p>
          </div>
          <div v-if="!project.design" class="github-link-div">
            <a :href="project.github" target="_blank">GitHub Repository</a>
          </div>
        </div>

        <div v-if="project.design" class="modal-container-design">
          <a class="modal-close-button-design" @click="$emit('viewProjectDetails')">
            &times;
          </a>
          <div class="img-div-design">
            <img :src="project.image" class='img-design'/>
          </div>
          <div class="modal-footer">{{ project.description }}</div>
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
      clickedProject: {},
    }
  },
  mounted: {
    setProject: function() {
      this.$data.clickedProject = this.project;
    }
  }
}
</script>

<style scoped>
  h1 {
    text-align: left;
  }
  p {
    font-size: 14px;
    line-height: normal;
  }
  a:hover {
    cursor: pointer;
  } 
  .img-div {
    height: 380px;
    margin: 20px;
    border: 1px solid black;
    overflow: hidden;
  }
  .img-div-design {
    max-height: 600px;
    margin: 20px;
    margin-top: 10px;
    /* border: 1px solid black; */
    overflow: auto;
  }
  .img {
    width: 100%;
  }
  .img-design {
    width: 100%;
  }
  .modal-mask {
    position: fixed;
    z-index: 9998;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, .7);
    display: table;
    transition: opacity .3s ease;
  }
  .modal-wrapper {
    display: table-cell;
    vertical-align: middle;
  }
  .modal-container {
    width: 800px;
    margin: 0px auto;
    padding: 20px 20px;
    background-color: wheat;
    border-radius: 2px;
    box-shadow: 0 20px 8px rgba(0, 0, 0, .33);
    transition: all .3s ease;
    font-family: Helvetica, Arial, sans-serif;
  }
  .modal-container-design {
    width: 800px;
    margin: 0px auto;
    padding: 20px 20px;
    background-color: wheat;
    border-radius: 2px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, .33);
    transition: all .3s ease;
    font-family: Helvetica, Arial, sans-serif;
  }
  .modal-header, .modal-body, .modal-footer, .github-link-div {
    margin-left: 20px;
  }
  .modal-close-button {
    float: left;
    margin: 0px;
  }

  /*
  * The following styles are auto-applied to elements with
  * transition="modal" when their visibility is toggled
  * by Vue.js.
  *
  * You can easily play with the modal transition by editing
  * these styles.
  */

  .modal-enter {
    opacity: 0;
  }

  .modal-leave-active {
    opacity: 0;
  }

  .modal-enter .modal-container,
  .modal-leave-active .modal-container {
    -webkit-transform: scale(1.1);
    transform: scale(1.1);
  }
</style>