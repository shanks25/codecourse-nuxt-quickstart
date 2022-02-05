<template>
<div class="post">
    <h1>
        <nuxt-link :to="{ name: 'posts-id', params:{id:post.id}}">{{post.title}}</nuxt-link>
    </h1>
    <p>{{post.body}}</p>
</div>
</template>

<script>
export default{
    props: {
        post:  Object,
    },
}
</script>