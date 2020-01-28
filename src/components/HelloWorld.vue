<template>
  <div>
    <img :src="image" width=200 height=200/>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      image: require('@/images/matt-violet.jpg')
    }
  }
}
</script>

<style scoped>
</style>
