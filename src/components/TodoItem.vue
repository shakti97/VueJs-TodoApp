<template>
    <div class='row todoItem'>
        <div class='col-md-9 todoTitle'>{{todo.title}}</div>
        <div class='col-md-1'><img src="https://fixmywp.com/wp-content/uploads/2013/07/mass-delete-wordpress-comments.png" :id="todo.id"  @click="removeItem" width=40px class='deleteImage' alt="Delete Image"></div>
        <div class="col-md-2"><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcT-O9A5S6OzKmZVyTfkZdGJ8u513NPtcwEfQG_YB8k470kvDZo1" :id="todo.id"  @click="editItem" class='editImage' width=20px alt="Edit Image"></div>
    </div>
</template>

<script>
export default {
    props : ["todo"],
    name : 'TodoItem',
    methods : {
        removeItem(event){
            this.$emit('removeItem',event.target.id);
        },
        editItem(event){
            this.$emit('editItem',event.target.id);
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
    .editImage{
        cursor : pointer;
    }
    .deleteImage{
        cursor : pointer;
    }
</style>