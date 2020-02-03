<template type="text/x-template" id="modal-template">
  <transition name="modal">
    <div class="modal-mask">
      <div class="modal-wrapper">
        <div v-if="project" class="modal-container">
          <a class="modal-default-button" @click="$emit('viewProjectDetails')">
            &times;
          </a>
          <div class="img-div">
            <img :src="project.image" class='img'/>
          </div>
          <div class="modal-header">
            <slot name="header">
              <h1>{{ project.title }}</h1>
            </slot>
          </div>

          <div class="modal-body">
            <slot name="body">
              <p>{{ project.details }}</p>
            </slot>
          </div>

          <div class="modal-footer">
            <slot name="footer">
              <p>{{ project.stack }}</p>
            </slot>
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
      width: 100%;
      height: 200px;
      margin-bottom: 20px;
      border: 1px solid black;
      overflow: hidden;
    }
  .img {
    width: 100%;
  }
  .modal-mask {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, .5);
  display: table;
  transition: opacity .3s ease;
  }

  .modal-wrapper {
    display: table-cell;
    vertical-align: middle;
  }

  .modal-container {
    width: 400px;
    margin: 0px auto;
    padding: 10px 20px;
    background-color: #fff;
    border-radius: 2px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, .33);
    transition: all .3s ease;
    font-family: Helvetica, Arial, sans-serif;
  }

  .modal-header h3 {
    margin-top: 0;
  }

  .modal-body {
    margin: 10px 0;
  }

  .modal-default-button {
    float: left;
    margin-bottom: 10px;
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