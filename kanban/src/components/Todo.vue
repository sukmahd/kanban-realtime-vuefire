<template lang="html">
  <div class="col">
    <div class="card">
      <div class="card-header bg-warning text-light">
        To Do
      </div>
      <div class="card-body">
        <!-- LIST JOB -->
        <div v-for="todo in todoTask" class="card mb-3">
          <div class="card-header text-light bg-dark">
            {{todo.title}}
          </div>
          <div class="card-body">
            <p>Point: {{todo.point}}</p>
            Assign To: {{todo.assignTo}}
          </div>
          <div class="card-footer bg-white">
            <button data-toggle="modal" data-target="#modalDetails" @click="taskDetails(todo)" class="btn btn-sm btn-info" type="button" name="button">Details</button>
          </div>
        </div>
        <!-- LIST JOB END -->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['todoTask'],
  methods: {
    taskDetails: function (data) {
      console.log('masuk sini')
      this.$emit('taskDetails', data)
    }
  }
}
</script>

<style lang="css">
</style>
