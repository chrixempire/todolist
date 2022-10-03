<template>
       <div class="Todo" :class="{'iscompleted': completed}">
        <div class="container">
            <input type="checkbox" @change="markedComplete">
        <div class="size">
       
       <div class="todoTitle">{{todo.title}}</div> 
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
    color: red;
    border: 3px solid red;
}
.Todo{
    background: rgb(229, 224, 224);
    padding: 10px ;
    /* border-bottom: 1px dotted black; */
    margin-top: 10px;
}
.container{
    font-size: 20px;
    color: black;
    display: flex;
    align-content: center;
    justify-content: space-between;
   
}
.todoTitle{
    /* border: 1px solid green; */
    margin: 0px;
    text-align: left;
    font-weight: 600;
    font-size: 15px;

}
input[type='checkbox']{
    width: 20px;
    height: 20px;
    margin: auto;
    margin-right: 10px;
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
    /* justify-content: center;  */
    gap: 10px;
    align-items: center;
    /* border: 1px solid purple; */
    width: 80%;
    margin-right: 10px;

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