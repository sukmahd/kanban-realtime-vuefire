<template lang="html">
  <div class="modal fade" id="modalDetails" tabindex="-1" role="dialog" aria-labelledby="modalDetails" aria-hidden="true">
    <div class="modal-dialog" role="document">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="modalDetails">Details Task: {{currentTask.title}}</h5>
          <button type="button" class="close" data-dismiss="modal" aria-label="Close">
            <span aria-hidden="true">&times;</span>
          </button>
        </div>
        <div class="modal-body">
          <p>Assign To: {{currentTask.assignTo}}</p>
          Description: {{currentTask.desc}}
          <p>Point: {{currentTask.point}}</p>
        </div>
        <div class="modal-footer">
          <button data-dismiss="modal" @click="setBackLog(currentTask)" v-if="currentTask.status == 1"  type="button" class="btn btn-danger">Back Log</button>
          <button data-dismiss="modal" @click="setTodo(currentTask)" v-if="currentTask.status == 0 || currentTask.status == 2"  type="button" class="btn btn-warning text-white">To Do</button>
          <button data-dismiss="modal" @click="setDoing(currentTask)" v-if="currentTask.status == 1 || currentTask.status == 3"  type="button" class="btn btn-primary">Doing</button>
          <button data-dismiss="modal" @click="setDone(currentTask)" v-if="currentTask.status == 2" type="button" class="btn btn-success">Done</button>
          <button data-dismiss="modal" @click="deleteTask(currentTask)" class="btn btn-danger" type="button" name="button">Delete</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['currentTask'],
  methods: {
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
      if (window.confirm('Are you sure want to delete this task?')) {
        this.$emit('deleteTask', data)
      }
    }
  }
}
</script>

<style lang="css">
</style>
