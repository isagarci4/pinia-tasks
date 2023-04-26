<script setup lang="ts">
import { useTaskStore } from './stores/TaskStore'
import TaskDetails from './components/TaskDetails.vue'

const taskStore = useTaskStore()
</script>

<template>
  <main>
    <header>
      <img src="./assets/pinia-logo.svg" alt="logo pinia: abacaxi com olhos e boca">
      <h1>Pinia Tasks</h1>
    </header>

    <div class="task-list">
      <div v-for="task in taskStore.tasks">
        <TaskDetails :task="task"/>
      </div>
    </div>
  </main>
</template>
<!-- 
<script>
  export default {
    
  }
</script> -->