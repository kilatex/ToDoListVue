<template>
    <div>
        <div v-bind:key="todo_prop.id" v-for="todo_prop in copyToDos" >
            <ListItemComponent v-bind:todo_prop="todo_prop" v-on:delete-todo="$emit('delete-todo',todo_prop.id)" />

        </div>
    </div>
</template>

<script>
import ListItemComponent from './ListItemComponent.vue'

export default {
    name: 'ListComponent',
    props: ['copyToDos'],
    mounted() {
    },
    components: { ListItemComponent }
}
</script>

<style>
</style>