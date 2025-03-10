<template>
  <BlogPost 
    v-for="post in posts" :key="post.id" :blogPostId="post.id" v-model:blogPostTitle="post.blogPostTitle" v-model:blogPostContent="post.blogPostContent" 
    @delete-blog-post="processDeletion"
  >
  
  </BlogPost>
</template>

<script setup>
  import { ref } from 'vue';
import BlogPost from './assets/BlogPost.vue';

function processDeletion(id){
  let index = posts.value.findIndex(item =>item.id == id)
  posts.value.splice(index, 1);
}

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
    },
    {
      "blogPostId": 4,
      "blogPostTitle": "Third Post",
      "blogPostContent": "And this is the content of the third post."
    }
])

// another things
</script>

<style scoped>

</style>