<script lang="ts">
import { defineComponent } from 'vue'

interface Task {
  text: string
  date: number
}

export default defineComponent({
  props: {
    tasks: {
      type: Array as () => Task[],
      required: true
    }
  }
})
</script>

<template>
  <ul class="tasks-list">
    <li v-for="task in tasks" :key="task.date" class="task">
      {{ task.text }}
    </li>
  </ul>
</template>

<style scoped>
.tasks-list {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 1rem;
  width: 100%;
}
.task {
  list-style: none;
  width: 100%;
  padding: 0.5rem;
  background-color: rgba(108, 143, 218, 0.473);
  border-radius: 8px;
}
</style>
