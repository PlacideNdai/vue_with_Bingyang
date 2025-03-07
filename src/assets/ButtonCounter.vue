<template>
    <button @click="count++">You clicked {{ count }} times</button>
</template>

<script setup>
import { ref } from 'vue';


    let count = ref(0);
</script>

<style scoped>
    button{
        background-color: purple;
        color:white;
        border: none;
        padding: 10px 20px;
        border-radius: 50px;
        cursor: pointer;
        margin-top: 10px;
        transition: all 0.2s;
    }

    button :hover{
        background: gold;
        box-shadow: 0 4px 8px lightgray;
    }
</style>