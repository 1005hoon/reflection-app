<template>
  <div class="post-lists">
    <h1>this is post lists</h1>
    <div v-for="post in posts" :key="post">
      <Post :post="post" />
    </div>
  </div>
</template>

<script>
import Post from './Post'

export default {
  props: ['posts'],
  components: { Post },
  setup(props) {
    console.log(props.posts)
  }
}
</script>

<style>

</style>