<script setup lang="ts">
import { useTaskStore } from './stores/TaskStore'
import TaskDetails from './components/TaskDetails.vue'
import { ref } from 'vue'

const taskStore = useTaskStore()
const filter = ref('all')
</script>

<template>
  <main>
    <header>
      <img src="./assets/pinia-logo.svg" alt="logo pinia: abacaxi com olhos e boca">
      <h1>Pinia Tasks</h1>
    </header>

    <nav class="filter">
      <button @click="filter = 'all'">All tasks</button>
      <button @click="filter = 'favs'">Fav tasks</button>
    </nav>

    <div class="task-list" v-if="filter === 'all'">
      <p>Your have {{ taskStore.totalCount }} tasks left to do</p>
      <div v-for="task in taskStore.tasks">
        <TaskDetails :task="task"/>
      </div>
    </div>
    <div class="task-list"  v-if="filter === 'favs'">
      <p>Your have {{ taskStore.favCount }} favs left to do</p>
      <div v-for="task in taskStore.favs">
        <TaskDetails :task="task"/>
      </div>
    </div>
  </main>
</template>