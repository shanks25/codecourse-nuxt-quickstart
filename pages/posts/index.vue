<template>
  <div>
    <h3>{{posts.length}} {{pluralize('post',posts.length)}} </h3>
      <Post v-for="post in posts" :key="post.id" :post="post"></Post>
      <a href="#" v-scroll-to="'body'">To top</a>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      posts: [],
    }
  },
  layout:'posts',
  head:{
      title:"Posts"
  },
  async asyncData() {
    let response = await axios.get('https://jsonplaceholder.typicode.com/posts')
    return {
      posts: response.data,
    }
  },
}
</script>