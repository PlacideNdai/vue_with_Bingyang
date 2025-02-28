<template>
  <div>
    
  </div>
</template>

<script setup>
import { ref } from 'vue';



  const users = ref([
  {
    "id": 1,
    "name": "John Doe",
    "age": 30,
    "active": true
  },
  {
    "id": 2,
    "name": "Jane Smith",
    "age": 25,
    "active": false
  },
  {
    "id": 3,
    "name": "Emily Johnson",
    "age": 28,
    "active": true
  },
  {
    "id": 4,
    "name": "Michael Brown",
    "age": 35,
    "active": false
  },
  {
    "id": 5,
    "name": "Linda Davis",
    "age": 40,
    "active": true
  }
]
)

  function sortuserByAge(){
    users.value.sort((a,b)=> a.age - b.age)
  }
</script>

<style scoped>
.inactive{
  color:red; 
  text-decoration:line-through; 
}
</style>