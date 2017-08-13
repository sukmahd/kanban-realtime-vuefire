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
              <input type="text" class="form-control form-control-sm" placeholder="title">
            </div>
            <div class="form-group">
              <label><h6>Description</h6></label>
              <input type="text" class="form-control form-control-sm" placeholder="Description">
            </div>
            <div class="form-group">
              <label><h6>Point</h6></label>
              <input type="number" class="form-control form-control-sm" placeholder="0">
            </div>
            <div class="form-group">
              <label><h6>Assign To</h6></label>
              <input type="text" class="form-control form-control-sm" placeholder="Assign To">
            </div>
          </form>
        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
          <button type="button" class="btn btn-primary">Save</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
}
</script>

<style lang="css">
</style>
