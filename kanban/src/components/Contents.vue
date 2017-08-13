<template lang="html">
  <div class="container">
    <div class="row">
      <!-- BACK LOG -->
      <backlog></backlog>
      <!-- BACKLOG END -->
      <!-- TODo -->
      <todo></todo>
      <!-- ToDo END -->
      <!-- DOING  -->
      <doing></doing>
      <!-- DOING END -->
      <!-- DONE -->
      <done></done>
      <!-- DONE END -->
    </div>
  </div>
</template>

<script>
import Backlog from '@/components/Backlog'
import Todo from '@/components/Todo'
import Doing from '@/components/Doing'
import Done from '@/components/Done'
export default {
  components: {
    Backlog,
    Todo,
    Doing,
    Done
  }
}
</script>

<style lang="css">
</style>
