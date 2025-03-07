<template>
    <div class="blog-post">
        <p>{{ message }}</p>
    
    <!-- id, title, content -->
     <h2>{{ id }} - {{ blogPostTitle }}</h2>
     <h4>{{ blogPostContent }}</h4>
    </div>
</template>

<script setup>
import { ref } from 'vue';

    let message = ref("This is a BlogPost Comp.")
    let props = defineProps(['id', 'blogPostTitle', 'blogPostContent']);
    // console.log(props.id)
    // defineProps({
    //     id: Number, 
    //     BlogPostTitle:String, 
    //     BlogPostContent: String, 
    // })
</script>

<style scoped>
    .blog-post{
        background-color: aqua;
        padding: 10px;
        margin-bottom:10px;
    }
</style>