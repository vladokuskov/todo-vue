<script setup lang="ts">
import TasksList from './components/TasksList.vue'
import AddTask from './components/AddTask.vue'

const tasks = [] as any

const handleFormSubmit = (text: string) => {
  const task = {
    text,
    date: Date.now()
  }
  tasks.push(task)
}
</script>

<template>
  <main class="main-wrapper">
    <header><h1>Todo app ⏲️</h1></header>
    <div class="content-wrapper">
      <AddTask :handleFormSubmit="handleFormSubmit" />
      <TasksList tasks="tasks" />
    </div>
  </main>
</template>

<style scoped>
.main-wrapper {
  width: full;
  margin: 0 auto;
  margin-top: 5rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 2rem;
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
