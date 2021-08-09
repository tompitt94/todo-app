<template>
  <div class="columns is-centered">
    <div class="column is-two-fifths is-centered">
      <form @submit.prevent="addTask">
        <input class="input m-2 is-rounded has-text-centered" type="text" placeholder="Whatcha gonna do?" v-model="taskName">
        <button class="button m-2 is-info is-rounded">Add Task</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AddTask',
  data () {
    return {
      taskName: ''
    }
  },
  methods: {
    addTask () {
      const task = {
        title: this.taskName,
        complete: false
      }
      this.$emit('taskToAdd', { task })

      this.taskName = ''
    }
  }
}
</script>

<style>

</style>
