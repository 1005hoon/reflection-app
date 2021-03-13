<template>
  <div class="post-lists">
    <h1>this is post lists</h1>
    <div v-for="post in posts" :key="post">
      <Post :post="post" />
    </div>
  </div>
</template>

<script>
import { onMounted, onUnmounted, onUpdated } from 'vue'
import Post from './Post'

export default {
  props: ['posts'],
  components: { Post },
  setup(props) {
    onMounted(() => {
      console.log('on mount')
    })
    onUnmounted(() => {
      console.log('on unmount')
    })
    onUpdated(() => {
      console.log('on updated')
    })
  },
}
</script>

<style>

</style>