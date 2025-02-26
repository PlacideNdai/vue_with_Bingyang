<template>
  <div>
    <h1>{{ message }}</h1>
    <button v-on:click="replaceText('v-on fun!')">Replace Text</button>
    <button @click="replaceText('v-on fun!')">Replace Text</button>

    <hr>
    <p>only numbers from user input</p>
    <input type="text" @keydown="handleInput($event)">


    <hr>

    <div style="width: 100px; height: 100px; background-color: aqua;" @contextmenu.prevent></div>

    <hr>

    <div id="mouseover" @mouseover="fun1">
      <textarea name="" id="" @mouseover.stop="fun2($event)">This is a text area</textarea>
    </div>
    <hr>

    <div>
      <input type="text" @keydown.enter="console.log('You pressed Enter')">
    </div>
    <hr>

    <div>
      <input type="text" @keydown.down="console.log('You pressed Enter')">
    </div>
    <hr>
    <div>
      <input type="text" @keydown.space="console.log('You pressed Enter')">
    </div>



  </div>
</template>

<script setup>
import { ref } from 'vue'

function fun1() {
  console.log('mouseover div');
}

function fun2(event) {
  // event.stopPropagation();

  console.log("mouse over event");
}
// 
function handleInput(event) {
  let keycode = event.keyCode;

  console.log(keycode);
  if (keycode < 48 || keycode > 57) {
    event.preventDefault();
  }
}
// 
let message = ref("Hello, On!")
function replaceText(msg) {
  message.value = msg;
}
</script>

<style scoped>
#mouseover {
  margin: 100px;
  text-align: right;
  background-color: purple;
  width: 300px;
  height: 300px;
}
</style>