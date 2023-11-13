<template>
    <div class="todo" v-bind:class="{completed: todo.completed}"  >
        <div class="todo-body" >
            <input id="todoCheck" v-on:change="changeCheck()" class="todo-checkbox" type="checkbox" v-bind:checked="todo.completed ? 'checked' : false">   
            {{ todo.title }}
        </div>
        <div class="todo-actions">
            <button @click="$emit('delete-todo',todo.id)">Delete</button>
        </div>
    </div>
</template>


<script>
export default {
    name: 'ListItemComponent',
    props: ['todo_prop'],
    data() {
        return {
            todo : this.todo_prop
        }
    },
    methods: {
    
        changeCheck(){
            console.log(this.todo)
            this.todo.completed = !this.todo.completed;
            console.log(this.todo)

        }
    },
}
</script>

<style scoped>
    .todo{
        border-bottom: solid 1px #ccc;
        padding: 10px;
        cursor: pointer;
    }
    .todo:not(.completed):hover{
        background-color: #eee;
    }
    .completed{
        color: #ccc;
        text-decoration: line-through;
    }

    .completed .todo-body{
        text-decoration: line-through;
    }
    .todo-body, .todo-actions{
        display: inline-block;
        vertical-align: top;
    }
    .todo-body{
        width: 85%;
    }
    .todo-actions{
        padding: 0 10px;
        width: 10%;
    }
    .todo .todo-checkbox{
        position: relative;
        top: 2px
    }
    button{
        border: none;
        border-radius: 3px;
        padding: 10px;
        background-color: #ccc;
        color: black;
        position: relative;
        top: -5px;
    }
    button:hover{
        background-color: #da2020;
        color: white;
    }
    .item-container{
        padding-bottom: 5px;
        padding-top: 5px;
    }
</style>