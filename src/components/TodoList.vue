<template>
    <div class='container'>
        <div v-for="todo in todos" :key="todo.id">
            <TodoItem :todo="todo" @removeItem="removeItem" @editItem="editItem"/>
        </div>
    </div>    
</template>

<script>
import TodoItem from "./TodoItem.vue";
export default {
    props : ["todos"],
    name : 'TodoList',
    components : {
        TodoItem
    },
    methods : {
        removeItem(e){
            this.$emit('removeItem',e);
        },
        editItem(e){
            this.$emit('editItem',e);
        }
    }

}
</script>

<style>

</style>