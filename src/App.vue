<template>
    <Header title="GYM Tracker"
            @toggle-add="toggleAdd"
            :btnToggle="showAddTask"
    
    />
    <div v-if="showAddTask">
      <AddTask @add-task="addTask" />
    </div>
    <Tasks 
      @delete-task="deleteTask" 
      @task-completed="isCompleted" 
      :tasks="tasks"
    />
</template>

<script>
import Header from './components/Header'
import Tasks from './components/Tasks'
import AddTask from './components/AddTask'

export default {
  name: 'App',
  components: {
        Header,
        Tasks,
        AddTask,
  },
 data() {
   return {
     tasks: [],
     showAddTask : false,
   }
 },
  methods: {
    toggleAdd() {
      this.showAddTask = !this.showAddTask
    },

    addTask(task) {
      this.tasks = [...this.tasks, task]
    },

    deleteTask(id) {
      if(confirm('Are you sure you want to delete')){
        this.tasks = this.tasks.filter((task) => task.id !== id)
        console.log('Task', id, 'deleted')
      }
    },

    isCompleted(id) {
      this.tasks = this.tasks.map((task) => task.id === id ?
         {...task, completed : !task.completed} : task
      )
      console.log('is completed', id)
    },
  },
 created() {
        this.tasks = [
      {
        'id' : 1,
        'title' : 'push ups',
        'day' : '22-07-2021',
        'completed': true
      },
      {
        'id' : 2,
        'title' : 'jogging',
        'day' : '25-07-2021',
        'completed': true
      },
      {
        'id' : 3,
        'title' : 'gyming',
        'day' : '30-07-2021',
        'completed': false
      },
    ]
 },
}
</script>

<style>
body {
  height: 100vh;
  background: #2c3e50;
  margin: 0;
  padding: 0;
  color: #f6faff;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  /* height: 100vh; */
}
</style>