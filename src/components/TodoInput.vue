<template>
    <div class='todoInput'>
        <input type="text" class='form-control' :value=taskitem @input='task' placeholder='Enter the new Task'>
        <button class="btn btn-primary addTask" @click='addTask'>{{operation}}</button>
        {{taskitem}}
    </div>
</template>

<script>
export default {
    props : ["taskitem","operation"],
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
            if(this.operation=="Add Task"){
            this.$emit('addTask',this.taskItem);
            }
            else{
                this.$emit('editTask',this.taskItem);
            }
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


