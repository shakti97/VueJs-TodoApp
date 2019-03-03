<template>
    <div class='todoInput'>
        <input type="text" class='form-control' @input='task' placeholder='Enter the new Task'>
        <button class="btn btn-primary addTask" @click='addTask'>Submit</button>
    </div>
</template>

<script>
export default {
    name : 'TodoInput',
    data(){
        return {
            taskItem : ''
        }
    },
    methods : {
        task(event){
            this.taskItem = event.target.value;
        },
        addTask(){
            this.$emit('addTask',this.taskItem);
        }
    }
}
</script>

<style>
    .addTask{
        margin-top : 2%;
        width : 20%;
    }
</style>


