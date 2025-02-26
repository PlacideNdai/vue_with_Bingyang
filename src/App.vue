<template>
  <div>
    <h1>{{ message }}</h1>
    <hr>
    <h1> Number: {{ number }}</h1>
  </div>
  <hr>

  <h1>Double Number 50: {{ doubleNum(120) }}</h1>
  <hr>
  <h1>Number * 2 = {{ number * 2 }}</h1>
  <hr>

  <h1>{{ number > 500 ? "Number greater than 500" : "Number is less than 500" }}</h1>

  <hr>
  <h2>{{ person }}</h2>

  <hr>
  <p v-text="number"></p>
  <hr>
  <h1 v-html="personGreet"></h1>


</template>

<script setup>
// script

let message = "Hello, Friends!"
let number = 510 / 2

function doubleNum(num) {
  return num * 2;
}


const person = {
  name: "John Doe",
  age: 30,
  contactDetails: {
    email: "john.doe@example.com",
    phone: "123-456-7890"
  }
};

let personGreet = "<h1>Sports<h1/>"
</script>



<style scoped></style>