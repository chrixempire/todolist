<template>
  <div class="cont">
    <addTodos @add-todo="addTodo"/>
  <todoList v-bind:todos="todos" @del-todo= "delTodo" />
  <p class="warn" v-show="this.todos.length === 0">Pleasee add a Todo to make up a todo list.</p>
  </div>
 </template>
 
 <script>
 

 import todoList from '../components/todoList'
 import addTodos from '../components/addTodos'
 import axios from 'axios'
 export default {
   name: 'HomeView',
   components: {
    todoList,
    addTodos,
   },
   data(){
     return{
       todos : [
       //   {
       //   id : 1,
       //   title : "Create a Todo-list with Vue Js",
       //   completed: false
       // },
       // {
       //   id : 2,
       //   title : "Work on My Technical Report",
       //   completed: true
       // },
       // {
       //   id : 3,
       //   title : "Research on my Project topics",
       //   completed: false
       // },
       // {
       //   id : 4,
       //   title : "Perfect on my Javascript Skills",
       //   completed: false
       // }
     ]
     
     }
   
   },
  methods:{
   async delTodo(id){
     console.log('i am working')
     
    //  axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
    //  .then(res => this.todos = this.todos.filter(todo => todo.id !== id))
    //  .catch(err => console.log(err))
   if(confirm('Are you sure?')){
    const res = await fetch(`https://jsonplaceholder.typicode.com/todos/${id}`,{
      method:'DELETE'
    })

    res.status === 200 ? (
    this.todos = this.todos.filter((todo) => todo.id !== id)) : alert('Error in deleting todo.')
   }
   },
   addTodo(newTodo){
     const { title, completed } = newTodo;
     axios.post('https://jsonplaceholder.typicode.com/todos', {
       title, 
       completed
     }) .then(res =>  this.todos.push(res.data))
     .catch(err => console.log(err))
     // this.todos= this.todos.push(newTodo)
     // this.todos = [...this.todos, res.data]
     console.log(newTodo)
   }
 
  },
  created(){
   axios.get('https://jsonplaceholder.typicode.com/todos?_limit=7')
   .then(res => this.todos = res.data )
   .catch(err => console.log(err))
  }
 
 }
 
 </script>
 
 <style>
 *{
   margin: 0px;
   padding: 0px;
   box-sizing: border-box;
 }
 .warn{
   color:red;
   font-size: 15px;
   font-weight: 600;
  text-align: center;
 }
 .cont{
  padding: 10px;
 }
 
 </style>
 
