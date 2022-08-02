<script>
import axios from "axios";
export de4fault {
  data: function () {
    return {
      posts: [],
    };
  },
  created: function () {
    this.indexPosts();
  },
  methods: {
    indexPosts: function () {
      axios.get("/posts.json").then((respons) => {
        this.posts = response.data;
        console.log("Posts: ", response.data);
      });
    },
  },
};
</script>

<template>
  <div>
    <h1>Blog Posts</h1>
    <div v-for="post in posts" v-bind:key="post.id">
      <h2>Title: {{ post.title }}</h2>
      <img v-bind:src="post.image_url" v-bind:alt="post.title" />
      <p>Chef: {{ post.chef }}</p>
      <a v-bind:href="`/posts/${post.id}`">More info</a>
    </div>
  </div>
</template>
