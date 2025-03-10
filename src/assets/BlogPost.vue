<template>
    <div class="blog-post">
        <p>{{ message }}</p>
    
    <!-- id, title, content -->
     <h2>{{ id }} - {{ blogPostTitle }}</h2>
     <h4>{{ blogPostContent }}</h4>
        <div>
            Change title: <input type="text" v-model="blogPostTitle">
        </div>
     <div>
        Change the content:
        <input type="text" v-model="blogPostContent">
     </div>
     <button @click="$emit('delete-blog-post', id)" >Delete Post</button>
     <button @click="emitDeketePostEvent(id)">Delete Post</button>
    </div>
</template>

<script setup>
import { ref } from 'vue';

    let message = ref("This is a BlogPost Comp.")
    let props = defineProps(['id']);
    const emit = defineEmits(['delete-blog-post'])
    let blogPostContent = defineModel('blogPostContent');
    let blogPostTitle = defineModel('blogPostTitle');


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

    input{
        width: 100%;
    }
</style>