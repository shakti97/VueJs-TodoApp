<template>
    <div class='row todoItem'>
        <div class='col-md-9 todoTitle'>{{todo.title}}</div>
        <div class='col-md-3' value=todo.id  @click="removeItem">&times;</div>
    </div>
</template>

<script>
export default {
    props : ["todo"],
    name : 'TodoItem',
    methods : {
        removeItem(){
            this.$emit('removeItem',event.target.value)
        }
    }
}
</script>

<style scoped>
    .todoTitle{
        text-align : left;
    }
    .todoItem{
        border : 1px solid rgb(34, 34, 65);
        border-radius: 5px;
        padding : 2%;
        margin: 1% 0%;
    }
</style>