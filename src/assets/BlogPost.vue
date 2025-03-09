<template>
    <div class="blog-post">
        <p>{{ message }}</p>
    
    <!-- id, title, content -->
     <h2>{{ id }} - {{ blogPostTitle }}</h2>
     <h4>{{ blogPostContent }}</h4>

     <button @click="$emit('delete-blog-post', id)" >Delete Post</button>
     <button @click="emitDeketePostEvent(id)">Delete Post</button>
    </div>
</template>

<script setup>
import { ref } from 'vue';

    let message = ref("This is a BlogPost Comp.")
    let props = defineProps(['id', 'blogPostTitle', 'blogPostContent']);
    const emit = defineEmits(['delete-blog-post'])


    function emitDeketePostEvent(id){
        emit('delete-blog-post', id);
    }
</script>

<style scoped>
    .blog-post{
        background-color: aqua;
        padding: 10px;
        margin-bottom:10px;
    }
</style>