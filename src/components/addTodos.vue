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
    margin-bottom: 20px;
}
input[type='text']{
    flex: 8;
    height: 50px;
    border: 1px solid grey;
    outline: none;
    font-size: 18px;
    padding: 20px;
    font-weight: 600;
}
input[type='submit']{
    flex: 3;
    color: blanchedalmond;
    font-size: 20px;
    background-color: black;
    border: none;
    outline: none;
    border-radius: 5px;
  
}

@media screen and (max-width: 600px) {
    form{
        display: block;
    }   
    input[type='text']{
    width: 100%;
    height: 50px;
    border: 1px solid grey;
    outline: none;
    font-size: 18px;
    padding: 20px;
}
input[type='submit']{
    width: 100%;
    height: 50px;
    margin-top: 10px;
    color: blanchedalmond;
    font-size: 20px;
    background-color: black;
    border: none;
    outline: none;
    border-radius: 5px;
  
} 
}
</style>