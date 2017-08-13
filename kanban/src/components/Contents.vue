<template lang="html">
  <div class="container">
    <div class="row">
      <!-- BACK LOG -->
      <backlog :backlogTask="backlogTask" @taskDetails="taskDetails"></backlog>
      <!-- BACKLOG END -->
      <!-- TODo -->
      <todo :todoTask="todoTask" @taskDetails="taskDetails"></todo>
      <!-- ToDo END -->
      <!-- DOING  -->
      <doing :doingTask="doingTask" @taskDetails="taskDetails"></doing>
      <!-- DOING END -->
      <!-- DONE -->
      <done :doneTask="doneTask" @taskDetails="taskDetails"></done>
      <!-- DONE END -->
      <ModalDetails @deleteTask="deleteTask" @setDoing="setDoing" @setTodo="setTodo" @setDone="setDone" @setBackLog="setBackLog" :currentTask="currentTask"></ModalDetails>
    </div>
  </div>
</template>

<script>
import ModalDetails from '@/components/ModalDetails'
import Backlog from '@/components/Backlog'
import Todo from '@/components/Todo'
import Doing from '@/components/Doing'
import Done from '@/components/Done'
export default {
  props: ['backlogTask', 'todoTask', 'doingTask', 'doneTask', 'currentTask'],
  components: {
    Backlog,
    Todo,
    Doing,
    Done,
    ModalDetails
  },
  methods: {
    taskDetails: function (data) {
      this.$emit('taskDetails', data)
    },
    setBackLog: function (data) {
      this.$emit('setBackLog', data)
    },
    setTodo: function (data) {
      this.$emit('setTodo', data)
    },
    setDoing: function (data) {
      this.$emit('setDoing', data)
    },
    setDone: function (data) {
      this.$emit('setDone', data)
    },
    deleteTask: function (data) {
      this.$emit('deleteTask', data)
    }
  }
}
</script>

<style lang="css">
</style>
