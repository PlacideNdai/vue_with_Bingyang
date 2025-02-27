<template>
  <div>
    <h1>{{ message }}</h1>
    <button @click="sortbyAge">Sort user by age</button>
    <ul>
      <li v-for="user in users" :key="user.id">
        {{ user.id }} - {{ user.name }} - {{ user.age }} - {{ user.isActive }}
      </li>
    </ul>


    <hr>


    <table border="1">
      <thead>
        <tr>
          <th>ID</th>
          <th>Name</th>
          <th>Age</th>
          <th>Active Status</th>
        </tr>
      </thead>

      <tbody>
        <tr v-for="(user, index) in users" :key="user.id">
          <td>{{ index }}</td>
          <td :class="{ inactive: !user.isActive }">{{ user.name }}</td>
          <td>{{ user.age }}</td>
          <td> <button @click="user.isActive = !user.isActive">{{ user.isActive ? "Deactivate" : "Restore" }}</button>
          </td>
        </tr>
      </tbody>
    </table>

    <hr>

    <div v-for="(value, key) in users[0]">{{key}} - {{ value }}</div>
  </div>
</template>

<script setup>
import { ref } from "vue"
let message = "Hello, Again!"

function sortbyAge() {
  users.value.sort((a, b) => a.age - b.age)
}



const users = ref([
  {
    id: 1,
    name: "John Doe",
    age: 30,
    isActive: true
  },
  {
    id: 2,
    name: "Jane Smith",
    age: 25,
    isActive: false
  },
  {
    id: 3,
    name: "Alice Johnson",
    age: 28,
    isActive: true
  },
  {
    id: 4,
    name: "Bob Brown",
    age: 35,
    isActive: false
  },
  {
    id: 5,
    name: "Charlie Green",
    age: 22,
    isActive: true
  }
]);

</script>

<style scoped>
.inactive {
  color: red;
  text-decoration: line-through;
}
</style>