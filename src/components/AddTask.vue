<script setup lang="ts">
import { ref } from 'vue'

const text = ref('')

const emit = defineEmits(['add-task'])

const addTask = () => {
  if (text.value.length !== 0) {
    emit('add-task', text.value)
  }

  text.value = ''
}
</script>

<template>
  <form v-on:submit.prevent="addTask">
    <input v-model="text" type="text" />
    <button type="submit">Add</button>
  </form>
</template>

<style scoped>
form {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1rem;
}

input {
  padding: 0.5rem;
  border-radius: 8px;
  background-color: rgb(212, 206, 198);
  border: none;
  font-family: Roboto;
  font-weight: 500;
  width: 100%;
  transition: background-color 0.3s;
}

input:hover,
input:focus {
  background-color: rgb(236, 232, 226);
}

button {
  padding: 0.5rem;
  border-radius: 8px;
  border: none;
  font-family: Roboto;
  font-weight: 500;
  background-color: rgb(88, 206, 88);
  color: white;
  transition: background-color 0.3s;
  cursor: pointer;
}

button:hover,
button:focus {
  background-color: rgb(51, 153, 51);
}
</style>
