<template lang="html">
  <div class="container">
    <nav class="navbar justify-content-between">
      <a class="navbar-brand">I-Fox Kanban</a>
      <form class="form-inline">
        <button class="btn btn-sm btn-outline-primary my-2 my-sm-0" type="button" data-toggle="modal" data-target="#addModal">Add Task</button>
      </form>
    </nav>
    <modal></modal>
  </div>
</template>

<script>
import Modal from '@/components/Modal'
export default {
  components: {
    Modal
  }
}
</script>

<style lang="css">
</style>
