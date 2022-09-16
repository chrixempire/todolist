<template>
    <div  v-for="todo in todos" :key="todo.id"  >
       <todoItem :todo="todo"></todoItem>
    </div>
</template>

<script>

import todoItem from './todoItem.vue'
export default {
    name: "todoList",
components: {
    todoItem
},
props:["todo"]
   
}
</script>

<style scoped>
div{
    background-color: red;
}
</style>