<template>
  <div>
    <h1>{{ message }}</h1>
    <h1>Welcome, {{ formData.name }}</h1>
    <form action="">
      <table>
        <tbody>
          <tr>
            <td>Name</td>
            <td><input type="text" v-model="formData.name"></td>
          </tr>
          <tr>
            <td>Gender</td>
            <td>
              <input type="radio" name="gender" value="female" v-model="formData.gender"> Female
              <input type="radio" name="gender" value="male" v-model="formData.gender"> Male
            </td>
          </tr>

          <tr>
            <td>Age</td>
            <td><input type="number" v-model.number="formData.age"></td>
          </tr>
          <tr>
            <td>Hobbies</td>
            <td>
              <input type="checkbox" name="hobbies" value="basketball" v-model="formData.hobbies"> Basketball
              <input type="checkbox" name="hobbies" value="football" v-model="formData.hobbies"> Football
              <input type="checkbox" name="hobbies" value="javascript" v-model="formData.hobbies"> JavaScript
            </td>
          </tr>
          <tr>
            <td>Profession</td>
            <td>
              <select name="profession" id="" v-model="formData.profession">
                <option value="">Select one</option>
                <option value="player">gamer</option>
                <option value="school">profesor</option>
              </select>
            </td>
          </tr>
          <tr>
            <td>Description</td>
            <td>
              <textarea name="description" id="" @keydown.enter="submitForm" v-model="formData.desc"></textarea>
            </td>
          </tr>
        </tbody>
      </table>
      <button type="submit" @click="submitForm" >Submit</button>
      <button type="reset" @click="resetForm">Reset</button>
    </form>
  </div>
</template>

<script setup>
import { ref } from 'vue';

let formData = ref({
  name: '',
  gender: '',
  age: '',
  hobbies: [],
  profession: '',
  desc: ''
})


function submitForm() {
  console.log(JSON.stringify(formData.value));
}

// submitting
function resetForm() {
  formData.value = {
    name: '',
    gender: '',
    age: '',
    hobbies: [],
    profession: '',
    desc: ''
  }
}

const message = ref('Hello, Vue!');
</script>

<style scoped></style>
