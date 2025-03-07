<template>
  <ButtonCounter></ButtonCounter>
  <ButtonCounter></ButtonCounter>

  <button-counter></button-counter>

  <hr>

  <div style="background: orange; padding: 5px;">
    This is the root component
  <CompA></CompA>
  <CompA></CompA>
</div>
</template>

<script setup>
  import ButtonCounter from './assets/ButtonCounter.vue';
import CompA from './assets/CompA.vue';
</script>

<style lang="scss" scoped>

</style>