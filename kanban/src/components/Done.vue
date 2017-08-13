<template lang="html">
  <div class="col">
    <div class="card">
      <div class="card-header bg-success text-light">
        Done
      </div>
      <div class="card-body">
        <!-- LIST JOB -->
        <div v-for="done in doneTask" class="card mb-3">
          <div class="card-header text-light bg-dark">
            {{done.title}}
          </div>
          <div class="card-body">
            <p>
              Point: {{done.point}}
            </p>
            Assign To: {{done.assignTo}}
          </div>
          <div class="card-footer bg-white">
            <button @click="taskDetails(done)" data-toggle="modal" data-target="#modalDetails" class="btn btn-sm btn-info" type="button" name="button">Details</button>
          </div>
        </div>
        <!-- LIST JOB END -->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['doneTask'],
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
