<template>
    <div  v-for="todo in todos" :key="todo.id"  >
    <todoItem :todo="todo"/>
    </div>
</template>

<script>
import todoItem from './todoItem.vue';

export default {
    name: "todoList",
    components:{
    todoItem,

},

   
}
</script>

<style scoped>

</style>