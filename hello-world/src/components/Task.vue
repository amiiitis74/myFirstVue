<template>
    <div :class="[task.reminder ? 'reminder' : '']">
        <h3>{{task.text}}
            <i @click="$emit('delete-task', task.id)" class="fas fa-times"></i>
        </h3>
        <p>{{task.day}}</p>
    </div>
</template>

<script>
export default {
    name: "Task",
    props:{
        task: Object
    },
    emits:['delete-task']
}
</script>

<style scoped>
div{
    border-radius: 5px;
    text-align: left;
    background-color: rgb(237, 237, 237);
    margin-top: 0.5rem;
    padding:0.5rem ;
}

.reminder{
    border-inline-start:5px solid green ;
}

h3{
    display: flex;
    justify-content: space-between;
}

.fas{
    color: red;
    cursor: pointer;
}
</style>