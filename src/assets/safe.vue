<template>
    <headerLayout/>
    <addTodos @add-todo="addTodo($event)"/>
    <todoList v-bind:todos="todos" @del-todo= "delTodo" />
    <p class="warn" v-show="this.todos.length === 0">Pleasee add a Todo to make up a todo list.</p>
   </template>
   
   <script>
   
   import headerLayout from './components/layout/headerLayout'
   import todoList from './components/todoList'
   import addTodos from './components/addTodos'
   import axios from 'axios'
   export default {
     name: 'App',
     components: {
      headerLayout,
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
     delTodo(id){
       console.log('i am working')
       // this.todos = this.todos.filter(todo => todo.id !== id)
       axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
       .then(res => this.todos = this.todos.filter(todo => todo.id !== id))
       .catch(err => console.log(err))
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
     axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5')
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
   
   </style>
   