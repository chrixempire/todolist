<template>
       <div class="Todo" :class="{'iscompleted': completed}">
        <p>
        <input type="checkbox" @change="markedComplete">
        {{todo.title}}
        <button @click="$emit('del-todo', todo.id)" class="del">
            X
        </button>
       </p>
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
.Todo p{
    padding: 20px;
    font-size: 20px;
    color: black;
   
}
input[type='checkbox']{
    width: 20px;
    height: 20px;
}
.Todo button{
    width: 50px;
    height: 50px;
    border-radius: 50%;
    background: red;
    display: flex;
    justify-content: center;
    align-items: center;
    border: none;
    outline: none;
    color: white;
    font-size: 25px;
    float:right;
    margin-bottom: 30px;
    cursor: pointer;
}
</style>