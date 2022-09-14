<template>
 <headerLayout/>
 <todoList v-for="todo in todos" :key="todo.id"/>
</template>

<script>

import headerLayout from './components/layout/headerLayout'
import todoList from './components/todoList'
export default {
  name: 'App',
  components: {
   headerLayout,
   todoList,
  },
  data(){
    return{
      todos : [
        {
        id : 1,
        title : "Create a Todo-list with Vue Js",
        completed: false
      },
      {
        id : 2,
        title : "Work on My Technical Report",
        completed: true
      },
      {
        id : 3,
        title : "Research on my Project topics",
        completed: false
      },
      {
        id : 4,
        title : "Perfect on my Javascript Skills",
        completed: false
      }
    ]
    }
  
  }
}
</script>

<style>
*{
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
}
</style>
