<template>
    <div class="container">
        <h1>{{title}}</h1>
        <Button text ="Add Task" theClass="btn-success"/>    
    </div>
</template>

<script> 
import Button from './Button.vue';

export default {
    name: "Header",
    props: {
        title: String
    },
    components: {
        Button
    }
}
</script>

<style scoped>
.container{
    margin: 2%;
    color: rgb(51, 51, 51);
    padding: 1rem;
    display: inline-flex;
    flex-direction: row;
    justify-content: space-between;
}

h1{
    font-weight: bolder;
}
</style>