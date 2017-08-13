<template>
  <div id="app">
    <headers @submitTask="submitTask"></headers>
    <contents @deleteTask="deleteTask" @setDone="setDone" @setDoing="setDoing" @setTodo="setTodo" @setBackLog="setBackLog" @taskDetails="taskDetails" :currentTask="currentTask" :backlogTask="backlogTask" :todoTask="todoTask" :doingTask="doingTask" :doneTask="doneTask"></contents>
  </div>
</template>

<script>
import Headers from '@/components/Headers'
import Contents from '@/components/Contents'
import * as firebase from 'firebase'

const config = {
  databaseURL: 'https://i-fox-kanban.firebaseio.com',
  projectId: 'i-fox-kanban'
}

const firebaseApp = firebase.initializeApp(config)
const db = firebaseApp.database()

export default {
  name: 'app',
  data: function () {
    return {
      currentTask: {
        title: '',
        content: '',
        point: 0,
        status: null,
        assignTo: ''
      }
    }
  },
  components: {
    Headers,
    Contents
  },
  firebase: {
    tasks: db.ref('tasks')
  },
  computed: {
    backlogTask () {
      return this.tasks.filter(function (task) {
        return task.status === 0
      })
    },
    todoTask () {
      return this.tasks.filter(function (task) {
        return task.status === 1
      })
    },
    doingTask () {
      return this.tasks.filter(function (task) {
        return task.status === 2
      })
    },
    doneTask () {
      return this.tasks.filter(function (task) {
        return task.status === 3
      })
    }
  },
  methods: {
    submitTask (data) {
      this.$firebaseRefs.tasks.push(data)
    },
    taskDetails (data) {
      this.currentTask = data
    },
    setBackLog (data) {
      this.$firebaseRefs.tasks.child(data['.key'])
      .child('status')
      .set(0)
    },
    setTodo (data) {
      this.$firebaseRefs.tasks.child(data['.key'])
      .child('status')
      .set(1)
    },
    setDoing (data) {
      this.$firebaseRefs.tasks.child(data['.key'])
      .child('status')
      .set(2)
    },
    setDone (data) {
      this.$firebaseRefs.tasks.child(data['.key'])
      .child('status')
      .set(3)
    },
    deleteTask (data) {
      this.$firebaseRefs.tasks.child(data['.key'])
      .remove()
    }
  }
}
</script>

<style>

</style>
