<template>
  <section class="section">
    <div class="container is-fluid has-text-centered">
      <add-task @taskToAdd="addTask"/>
    </div>
    <hr>
    <div>
      <dl class="has-text-centered">
        <dt v-for="task in tasks" :key="task.title" :style="task.complete ? 'text-decoration: line-through;' : ''">
          {{ task.title }}
      <!-- Complete -->
          <span class="icon has-text-success ml-2 mt-2" v-if="!task.complete" @click="task.complete = true">
            <i class="fas fa-check-circle is-clickable"></i>
          </span>
      <!-- Delete -->
          <span class="icon has-text-danger ml-2 mt-2" @click="this.tasks.pop(task)">
            <i class="fas fa-trash is-clickable"></i>
          </span>
        </dt>
      </dl>
    </div>
  </section>
</template>

<script>
import AddTask from './components/AddTask.vue'

export default {
  name: 'App',
  components: {
    AddTask
  },
  data () {
    return {
      tasks: []
    }
  },
  methods: {
    addTask (eventData) {
      const task = {
        ...eventData.task
      }
      this.tasks.push(task)
    }
  }
}
</script>

<style>

</style>
