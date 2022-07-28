<template>
    <button @click="onClick()"  :class="[theClass,'btn', 'btn-sm']">{{text}}</button>
</template>

<script>
export default {
    name : "Button",
    props: {
        text: String,
        theClass: String,
    },
    methods:{
        onClick(){
            console.log("clicked!");
        }
    }
}
</script>

<style scoped>

</style>