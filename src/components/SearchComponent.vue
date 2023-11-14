<template>
    <div class="searchh">
        <div class="search-container">
            <input type="text" class="search-to-do" v-model="query" v-on:input="$emit('query-change',query)">
        </div>
    </div>
</template>

<script>
export default {
    name : 'SearchComponent',
    data() {
        return {
            query:''
        }
    },
}
</script>

<style scoped>
    .searchh
    {
        display: flex;
        justify-content: center;
    }
   .search-to-do{
        width: 500px;
        padding: 5px;
   }
   

</style>