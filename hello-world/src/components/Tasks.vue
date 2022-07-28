<template>
    <div class="container">
        <div v-for="task in tasks" :key="task.id">
            <Task
            :task="task"
            @delete-task="$emit('delete-task',task.id)" 
             />
        </div>      
    </div>
</template> 

<script>
import Task from './Task.vue'
export default {
  components: { Task },
    naem: "Tasks",
    props:{
        tasks : Array
    },
    emits:['delete-task']
}
</script>