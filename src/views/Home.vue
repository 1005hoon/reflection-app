<template>
  <div class="home">
    <h1>Home</h1>
    <PostList v-if="showPosts" :posts="posts" />
    <button @click="showPosts = !showPosts">toggle posts</button>
    <button @click="posts.pop()">Delete Post</button>
  </div>
</template>

<script>
import { ref } from 'vue'
import PostList from '../components/PostList'

export default {
  name: 'Home',
  components: { PostList },
  setup() {
    const posts = ref([]);
    const showPosts = ref(true)
    return { posts, showPosts }
  },
}
</script>
