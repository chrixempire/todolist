<template>
       <div class="Todo" :class="{'iscompleted': completed}">
        <div class="container">
        <div class="size">
        <input type="checkbox" @change="markedComplete">
        {{todo.title}}
        </div>
        <button @click="$emit('del-todo', todo.id)" class="del">
            X
        </button>
    </div>
    </div>
</template>

<script>
export default {
    name: "todoItem",
    props:[ "todo"],
    data(){
        return{
            completed : this.todo.completed
        }
    },
    methods:{
        markedComplete(){
            console.log('i am working')
           this.completed = !this.completed
        }
    }
}
</script>

<style scoped>
.iscompleted{
    text-decoration: line-through;
}
.Todo{
    background: grey;
    padding: 10px;
    border-bottom: 1px dotted black;
}
.container{
    font-size: 20px;
    color: black;
    display: flex;
    align-content: center;
    justify-content: space-between;
   
}
input[type='checkbox']{
    width: 20px;
    height: 20px;
}
.Todo button{
    width: 35px;
    height: 35px;
    border-radius: 50%;
    background: red;
    display: flex;
    justify-content: center;
    align-items: center;
    border: none;
    outline: none;
    color: white;
    font-size: 15px;
    cursor: pointer;
    
}
.size{
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10px;
}
@media screen and (max-width: 600px) {
    .container{
    font-size: 15px;
    color: black;
    display: flex;
    align-content: center;
    justify-content: space-between;
   
}   
}
</style>