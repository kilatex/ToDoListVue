<template>
    <div id="add-container" class="add-container">
        <form >
            <input type="text" name="add" id="add" class="add" v-model="title">
            <button class="send-to-do" @click="addToDo">Add</button>
        </form>
    </div>
</template>


<script>
import {uuid} from 'vue-uuid'
export default {
    name: 'AddToDoComponent',
    data() {
        return {
            title: ''    
        }
    },
    methods: {
        addToDo(e){
            e.preventDefault();

            const newTodo = {
                id: uuid.v4() ,
                title: this.title,
                completed: false
            }

            this.title='';
            this.$emit('add-todo',newTodo)

        }

    },
}
</script>

<style scoped>
    .add-container{
        padding: 10px;
    }
    
    input.add{
        padding: 10px;
        outline: none;
        border: solid 1px #ccc;
        width: 80%;
    }
    .send-to-do{
        margin-left: 10px;
        padding: 9px;
        width: 14%;
        border: none;
        cursor: pointer;
    }
</style>