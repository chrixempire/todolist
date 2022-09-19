<template>
    <div  v-for="todo in todos" :key="todo.id"  >
       <todoItem :todo="todo" @del-todo="$emit('del-todo', todo.id)" ></todoItem>
    </div>
</template>

<script>

import todoItem from './todoItem.vue'
export default {
    name: "todoList",
components: {
    todoItem
},
props:["todos"],

}
</script>

<style scoped>
div{
    background-color: red;
}
</style>