<template>
    <form action="" class="addtodo"  @submit="Addtodo">
        <input type="text" name="title" v-model="title"  placeholder="Add Todos ...">
        <input type="submit" value="submit">
    </form>
 </template>

<script>
    // import uuid from 'uuid'
export default {
    name: 'addTodos',
    data(){
        return{
            title: ''
        }
    },
    methods:{
        Addtodo(e){
            e.preventDefault();
            const newTodo = {
                title:this.title,
                completed: false,
            }
            this.$emit('add-todo', newTodo)
            this.title = ''
 
      }
        
    }
}
</script>

<style scoped>
form{
    display: flex;
}
input[type='text']{
    flex: 8;
    height: 50px;
    border: 1px solid grey;
    outline: none;
    font-size: 18px;
    padding: 20px;
}
input[type='submit']{
    flex: 3;
    color: blanchedalmond;
    font-size: 20px;
    background-color: red;
    border: none;
    outline: none;
    border-radius: 5px;
}
</style>