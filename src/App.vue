<template>
  <div>
    <h2>Message: {{ message }}</h2>
    <h2>Number: {{ number }}</h2>

    <button @click="changeMessageUpperCase">Change message to upper Case</button>
    <button @click="IncreamentNum">Increament Number</button>


    <hr>
    <h2>Name: {{ player.name }}</h2>
    <h2>Hobbies: {{ player.hobbies }}</h2>

    <button @click="changeMessageUpperCase">Change to UpperCase</button>
    <button @click="changePlayer">Change Player</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';
let message = ref("Hello, Reactors")
let number = ref(10)

function changeMessageUpperCase() {
  player.value.name = player.value.name.toUpperCase();
}

function changeHobbies() {
  player.value.core.engine = "V8"
}

function changePlayer() {
  player.value = {
    "name": "Morgan",
    "age": 22,
    "position": "Forward",
    "stats": {
      "goals": 15,
      "assists": 7,
      "matches": 20
    }
  }

}

function IncreamentNum() {
  number.value += 10;
  console.log(number.value);
}

let player = ref({
  age: 45,
  name: "John D",
  hobbies: ["chess", "programming", "reading"],
  core: {
    engine: "V6",
    sEngine: "V7"
  }
})
</script>

<style scoped></style>