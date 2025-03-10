<template>
  <div>
    <h1>{{ message }}</h1>
    <div style="background: orange; padding-left: 10px;">
      <CompA></CompA>
    </div>
  </div>
</template>

<script setup>
  import { provide, readonly, ref } from 'vue';
import CompA from './assets/CompA.vue';

  let message = ref("Hello, Friends - Provide/Inject");

  function updateMessage(){
    message.value = "Hello provided update";
  }

  provide('msg', {message, updateMessage});

  let count = ref(0);

  provide('read-only-count', readonly(count));

</script>

<style scoped>

</style>