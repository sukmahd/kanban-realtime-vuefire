<template lang="html">
  <div class="modal fade" id="addModal" tabindex="-1" role="dialog" aria-labelledby="addModal" aria-hidden="true">
    <div class="modal-dialog" role="document">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="addModalLabel">Add New Task</h5>
          <button type="button" class="close" data-dismiss="modal" aria-label="Close">
            <span aria-hidden="true">&times;</span>
          </button>
        </div>
        <div class="modal-body">
          <form class="">
            <div class="form-group">
              <label><h6>Title</h6></label>
              <input v-model="formTask.title" type="text" class="form-control form-control-sm" placeholder="title">
            </div>
            <div class="form-group">
              <label><h6>Description</h6></label>
              <input v-model="formTask.desc" type="text" class="form-control form-control-sm" placeholder="Description">
            </div>
            <div class="form-group">
              <label><h6>Point</h6></label>
              <input v-model="formTask.point" type="number" class="form-control form-control-sm" placeholder="0">
            </div>
            <div class="form-group">
              <label><h6>Assign To</h6></label>
              <input v-model="formTask.assignTo" type="text" class="form-control form-control-sm" placeholder="Assign To">
            </div>
          </form>
        </div>
        <div class="modal-footer">
          <button  type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
          <button @click="submitTask()" type="button" class="btn btn-primary" data-dismiss="modal">Save</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      formTask: {
        title: '',
        desc: '',
        point: 0,
        assignTo: '',
        status: 0
      }
    }
  },
  methods: {
    submitTask () {
      this.$emit('submitTask', this.formTask)
      this.formTask.title = ''
      this.formTask.desc = ''
      this.formTask.point = 0
      this.formTask.assignTo = ''
      console.log('masuk sini 1')
    }
  }
}
</script>

<style lang="css">
</style>
