<template>
    <div>
        <div class="header" id="header">
            <SearchComponent v-on:query-change="querySearch"/>

        </div>
        <div class="container" id="container">
            <h1>To Do list with VueJs</h1>

            <AddToDoComponent v-on:add-todo="addToDo"/>
            <ListComponent v-bind:copyToDos="copyToDos" v-on:delete-todo="deleteTodo"/>
        </div>


    </div>
</template>


<script>
import AddToDoComponent from './AddToDoComponent.vue';
import ListComponent from './ListComponent.vue';
import SearchComponent from './SearchComponent.vue';
export default {
    name: 'HomePage',
    components: {
        AddToDoComponent, ListComponent, SearchComponent
    },
    data() {
        return {
            toDos: [
                {
                    id:0,
                    title: 'Comprar la cena',
                    completed: false
                },
                {
                    id:1,
                    title: 'Contestar emails',
                    completed: true
                },
                {
                    id:2,
                    title: 'Jugar Fútbol',
                    completed: false
                }
            ],
            copyToDos:[],
           
        }

     
        
    },
    created() {
            this.copyToDos = [... this.toDos]
    },
    methods: {
        deleteTodo(id){
            this.toDos = this.toDos.filter(todo => todo.id != id);
            this.copyToDos = [... this.toDos];
        },
        addToDo(todo){
            this.toDos.push(todo);
            this.copyToDos = [...this.toDos]
        },
        querySearch(query){
            if(query.trim() === ''){
                this.copyToDos = [...this.toDos];
            }else{
                const temp = this.toDos.filter(toDos => {
                    return toDos.title.includes(query)
                });
                this.copyToDos = [...temp];
            }
        }
    },
}
</script>

<style scoped>
    *{
        box-sizing: border-box;
    }
    body{
        font-family: Arial, Helvetica sans-serif;
        font-size: 1.5em;
        padding: 0;
        margin: 0;
    }
    .container{
        border: solid 1px #ccc;
        width: 600px;
        margin: 100px auto;
    }
    .header{
        background: black;
        padding: 10px;
    }
    h1{
        padding: 0 10px;
    }
</style>