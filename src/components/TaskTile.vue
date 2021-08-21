<template>
  <div class="box notification" :class="this.complete ? 'notification is-success' : 'notification'">
    <button class="delete" @click="taskComplete"></button>
    <h2>{{ this.task }}</h2>
  </div>
</template>

<script>
export default {
  name: 'TaskTile',
  props: {
    taskName: {
      type: String
    },
    taskDone: {
      type: Boolean
    }
  },
  data () {
    return {
      task: this.taskName,
      complete: this.taskDone
    }
  },
  methods: {
    taskComplete () {
      this.complete = true
    }
  }
}
</script>

<style>

</style>
