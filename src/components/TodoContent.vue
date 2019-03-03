<template>
        <div class="todoContent">
            <TodoInput @addTask="addTask"/>
            <TodoList :todos="todos"  @removeItem="removeItem"/>
            {{removingElement}}
            {{todos}}
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
            if(e==''){
                return;
            }
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
            this.todos = this.todos.filter((item) =>{console.log(item); if(item.id !=e){return item}});
            console.log(this.todos);
        }
    }

}
</script>

<style >
    .todoContent{
        margin: 2% 20%;
    }
</style>


