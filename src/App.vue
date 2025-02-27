<template>
  <div>
    <h1>{{ message }}</h1>
    <p>Why did the chicken close the road?</p>
    <button style="width: 200px;" @click="showanswer = !showanswer">{{ showanswer ? "Hide the answer" : "Show the answer"
      }}</button>
  </div>

  <div v-if="showanswer">There was chick fia on this side.</div>
  <div v-show="showanswer">You see me</div>

  <hr>
  <div v-if="Math.random() > 0.5">You see me</div>
  <div v-else>Now you don't
  </div>
</template>

<script setup>
import { ref } from "vue";
let showanswer = ref(false);

</script>

<style lang="scss" scoped></style>