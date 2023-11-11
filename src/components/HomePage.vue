<template>
    <div>
        <h1>To Do list with VueJs</h1>
        <SearchComponent/> 
        <AddToDoComponent/>
        <ListComponent/>

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
    }
}
</script>

<style scoped>


</style>