<template>
  <div>
    <h1>{{ message }}</h1>
    <hr>
    <img :src="imageUrls" alt="">
    <hr>
    <img v-bind:src="imageUrls" alt="">
    <button @click="changeImg">Change Image</button>
    <hr>
    <input type="text" :value="defaultInput">

    <hr>

    <p :class="className">Harry Potter</p>
    <p :class="{inactive: isInActive, center: isCenter }">Placide Ndai</p>
    <p :class="['active', 'center']">John</p>
  </div>
</template>

<script setup>
import { ref } from 'vue'

let message = "Hello, Friends"
let imageUrls = ref("/public/img/banner_1.jpg")

function changeImg() {
  imageUrls.value = "/public/img/banner_2.jpg";
}


let defaultInput = "write something"

// classes 
let className = 'active'

let isInActive = ref(true)
let isCenter = ref(false)


</script>



<style scoped>
img {
  max-width: 300px;
}

.active {
  color: green;
}

.inactive {
  color: red;
  text-decoration: line-through;
}

.center{
  text-align: center;
}
</style>