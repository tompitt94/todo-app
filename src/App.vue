<template>
  <section class="section">
    <div class="container is-fluid has-text-centered">
      <add-task @taskToAdd="addTask"/>
    </div>
    <hr>
    <div class="section has-text-centered">
      <div class="columns is-multiline has-text-centered">
        <div
          class="column is-3"
          v-for="task in tasks" :key="task.title">
          <task-tile
            :taskName="task.title"
            :taskDone="task.complete"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import AddTask from './components/AddTask.vue'
import TaskTile from './components/TaskTile.vue'

export default {
  name: 'App',
  components: {
    AddTask,
    TaskTile
  },
  data () {
    return {
      tasks: []
    }
  },
  mounted () {
    document.title = 'Todo App'
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
