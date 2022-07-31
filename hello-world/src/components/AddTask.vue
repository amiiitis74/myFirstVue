<template>
    <form @submit="onSubmit">
        <div class="form-group">
            <label for="text">Task</label>
            <input v-model="text" class="form-control" type="text" name="text" placeholder="Add your task" />
        </div>
        <div class="form-group">
            <label for="day">Day & Time</label>
            <input v-model="day" class="form-control" type="text" name="day" placeholder="Add Date" />
        </div>
        <div class="form-group">
            <input v-model="reminder" type="checkbox" />
            <label class="form-check-label" for="reminder"> Set reminder</label>
        </div>
        <div class="form-group">
            <button type="submit" class="btn btn-dark">Save Task</button>
        </div>
    </form>
</template>

<script>
export default {
    name: "AddTask",
    data(){
        return {
            text: '',
            day: '',
            reminder: false
        }
    },
    methods:{
        onSubmit(e){
            e.preventDefault();

            if(!this.text){
                alert("Please add your task");
            }

            const newTask = {
                id: Math.floor(Math.random() * 100),
                text: this.text,
                day: this.day,
                reminder: this.reminder
            }

            console.log(newTask);

            this.text = '';
            this.day = '';
            this.reminder = false;

        }
    }

}
</script>

<style scoped>
    form{
        text-align: left;
        padding: 1rem;
    }

    .form-group{
        margin-top: 1rem;
    }
</style>