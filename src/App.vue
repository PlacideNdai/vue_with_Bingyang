<template>
  <!-- <BlogPost
      id="1" 
      blogPostTitle="What is a muggle" 
      blogPostContent="A muggle is a person who lacks any sort of magical ability..."
   ></BlogPost>

  <BlogPost 
    :id="blogPostId" 
    :blog-post-title="blogPostTitle"
    :blog-post-content="blogPOSTContent">
  </BlogPost> -->

  <hr>

  <BlogPost v-for="post in posts" :id="post.id" :key="post.id" :blog-post-title="post.blogPostTitle" :blog-post-content="post.blogPostContent">
  </BlogPost>

  <hr>
  second 
  <BlogPost 
    v-for="post in posts" :key="post.id" v-bind="post" 
  >
  
  </BlogPost>
</template>

<script setup>
  import { ref } from 'vue';
import BlogPost from './assets/BlogPost.vue';


let posts = ref([

{
      "blogPostId": 1,
      "blogPostTitle": "First Post",
      "blogPostContent": "This is the content of the first post."
    },
    {
      "blogPostId": 2,
      "blogPostTitle": "Second Post",
      "blogPostContent": "Here's the content of the second post."
    },
    {
      "blogPostId": 3,
      "blogPostTitle": "Third Post",
      "blogPostContent": "And this is the content of the third post."
    }
])

  let blogPostId = ref(1);
  let blogPostTitle = ref("Something about news");
  let blogPOSTContent = ref("Something in the news explained here");

// another things
</script>

<style scoped>

</style>