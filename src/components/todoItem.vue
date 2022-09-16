<template>
    <div class="Todo" :class="{'iscompleted':todo.completed}">
        <p>
        <input type="checkbox" @click="markcomplete">
        {{todo.title}}
        <button >
            X
        </button>
       </p>
    </div>
</template>

<script>
export default {
    name: "todoItem",
    props:['todo'],
    methods:{
        markcomplete(){
           console.log("i am working");
           this.todo.completed = !this.todo.completed
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
    font-size: 30px;
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
    float: right;
    cursor: pointer;
}
</style>