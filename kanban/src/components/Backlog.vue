<template lang="html">
  <div class="col">
    <div class="card">
      <div class="card-header bg-danger text-light">
        Back Log
      </div>
      <div class="card-body">
        <!-- LIST JOB -->
        <div v-for="backlog in backlogTask" class="card mb-3">
          <div class="card-header text-light bg-dark">
            {{backlog.title}}
          </div>
          <div class="card-body">
            <p>Point: {{backlog.point}}</p>
            Assign To: {{backlog.assignTo}}
          </div>
          <div class="card-footer bg-white">
            <button @click="taskDetails(backlog)" data-toggle="modal" data-target="#modalDetails" class="btn btn-sm btn-info" type="button" name="button">Details</button>
          </div>
        </div>
        <!-- LIST JOB END -->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['backlogTask'],
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
