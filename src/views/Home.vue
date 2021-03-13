<template>
  <div class="home">
    <h1>Home</h1>
    <div v-if="error">{{error}}</div>
    <div v-if="posts.length">
      <PostList :posts="posts" />
    </div>
    <div v-else>Loading . . .</div>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue'
import PostList from '../components/PostList'

export default {
  name: 'Home',
  components: { PostList },
  setup() {
    const posts = ref([]);
    const error = ref(null);

    const fetchData = async() => {
      try {
        const res = await fetch('http://localhost:3000/posts');
        
        if (!res.ok) {
          throw Error('No data available')
        }
        posts.value = await res.json()
      } catch (error) {
        error.value = error.message
        console.log(error.value)
      }
    }
    fetchData()

    return { posts, error }
  },
}
</script>
