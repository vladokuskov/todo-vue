<script setup lang="ts">
import TasksList from './components/TasksList.vue'
import AddTask from './components/AddTask.vue'
import { ref } from 'vue'

interface Task {
  text: string
  date: number
}

const tasks = ref<Task[]>([])

const handleFormSubmit = (text: string) => {
  const task = {
    text,
    date: Date.now()
  }
  tasks.value.push(task)
}
</script>

<template>
  <main class="main-wrapper">
    <header>
      <h1>ToDo Vue ⏲️</h1>
    </header>
    <div class="content-wrapper">
      <AddTask :onAdd-task="handleFormSubmit" />
      <TasksList :tasks="tasks" />
    </div>
  </main>
</template>

<style scoped>
.main-wrapper {
  width: 100%;
  margin: 0 auto;
  margin-top: 5rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 2rem;
  padding: 0.5rem;
}

.content-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 2rem;
}

h1 {
  text-align: center;
  font-weight: 500;
}
</style>
