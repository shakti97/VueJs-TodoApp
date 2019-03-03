<template>
        <div class="todoContent">
            <TodoInput @addTask="addTask"/>
            <TodoList :todos="todos"  @removeItem="removeItem"/>
        </div>
</template>

<script>
import TodoInput from  './TodoInput.vue';
import TodoList from "./TodoList.vue";

export default {
    name : 'TodoContent',
    data(){
        return{
            todoItem : 1,
            task : 'No task',
            todos : [],
            removingElement : ''
        }
    },
    components : {
        TodoInput,
        TodoList
    },
    methods : {
        addTask(e){
            this.task=e;
            var todoObject={
                id : this.todoItem,
                title : this.task
            }
            
            this.todos.push(todoObject);
            this.todoItem++;
        },
        removeItem(e){
            this.removingElement=e;
        }
    }

}
</script>

<style >
    .todoContent{
        margin: 2% 20%;
    }
</style>


