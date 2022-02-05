<template>
  <div class="div">
    <Post :post="post"></Post>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      post: null,
    }
  },
  head() {
    return {
      title: this.post.title,
    }
  },

  async asyncData({ params, error }) {
    try {
      let response = await axios.get(
        `https://jsonplaceholder.typicode.com/posts/${params.id}`
      )
      return {
        post: response.data,
      }
    } catch (e) {
      error({
        statusCode: e.response.status,
      })
    }
  },
}
</script>
