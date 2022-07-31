<template>
  <div id="app" >
    <div class="myPlace">
      <AddTask />
      <Header title="Task Tracker"/>
      <Tasks  
      @delete-task="deleteTask" 
      :tasks="tasks" />
    </div>    
  </div>
</template>

<script>
import AddTask from './components/AddTask.vue';
import Header from './components/Header.vue';
import Tasks from './components/Tasks.vue';


export default {
  name: "App",
  components: {
    Header,
    Tasks,
    AddTask
  },
    AddTask(){
    return {
      tasks : []
    }
  },
  methods:{
    deleteTask(id) {
      if(confirm("Are you sure to delete the task?")){
        console.log("delete task",id);
        this.tasks = this.tasks.filter((task)=>task.id !== id);
      }
    }
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: 'Dockter visiting',
        day: 'March 1st at 2PM',
        reminder: true
      },
      {
        id: 2,
        text: 'Studing the exam',
        day: 'March 3rd at 8AM',
        reminder: true
      },
      {
        id: 3,
        text: 'Shopping wiht friends',
        day: 'Feb 21st at 12PM',
        reminder: false
      }
    ]
  }
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.myPlace{
  border: 1px solid darkgrey;
  border-radius: 5px;
  margin: 0.5rem;
}

</style>
