<template lang="html">
  <div class="col">
    <div class="card">
      <div class="card-header bg-primary text-light">
        Doing
      </div>
      <div class="card-body">
        <!-- LIST JOB -->
        <div v-for="doing in doingTask" class="card mb-3">
          <div class="card-header text-light bg-dark">
            {{doing.title}}
          </div>
          <div class="card-body">
            <p>Point: {{doing.point}}</p>
            Assign To: {{doing.assignTo}}
          </div>
          <div class="card-footer bg-white">
            <button @click="taskDetails(doing)" data-toggle="modal" data-target="#modalDetails" class="btn btn-sm btn-info" type="button" name="button">Details</button>
          </div>
        </div>
        <!-- LIST JOB END -->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['doingTask'],
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
