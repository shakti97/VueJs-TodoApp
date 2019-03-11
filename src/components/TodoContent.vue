<template>
        <div class="todoContent">
            <TodoInput :taskitem="task" :operation="operation" @addTask="addTask" @editTask="editTask"/>
            <TodoList :todos="todos"  @removeItem="removeItem" @editItem="editItem"/>
            <!-- {{removingElement}}
            {{todos}} -->
            {{task}}
            <!-- {{editElement}} -->
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
            task : '',
            operation : 'Add Task',
            todos : [],
            removingElement : '',
            editElement:''
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
            // console.log('e',e);
            this.todos = this.todos.filter((item) =>{ if(item.id !=e){return item}});
            // console.log(this.todos);
        },
        editItem(e){
            this.editElement=e;
            var selectedElement=this.todos.filter((item)=>{if(item.id==e){return item}});
            // console.log(selectedElement);
            this.task=selectedElement[0].title;
            this.operation='Edit Task'
        },
        editTask(e){
            if(e==''){
                return;
            }
            var todoObject={
                id : this.editElement,
                title : e
            }
            this.todos[this.editElement-1]=todoObject;
            // console.log(this.todos);

        }
    }

}
</script>

<style >
    .todoContent{
        margin: 2% 20%;
    }
</style>


