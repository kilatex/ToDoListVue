<template>
    <div>
        <div v-bind:key="todo.id" v-for="todo in copyToDos" >
            <ListItemComponent v-bind:todo="todo"/>

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