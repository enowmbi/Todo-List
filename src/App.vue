<template>
<div id="app" class="container">
<Header />
<AddTodo v-on:add-todo="addTodoItem"/>
<Todos v-bind:todos="todos" v-on:del-todo="deleteTodoItem" />
<Footer msg="Copyright(c) 2019, Enow B. Mbi"/>
</div>
</template>

<script>
import Header from './components/layout/Header'
import AddTodo from './components/AddTodo'
import Footer from './components/layout/Footer'
import Todos from './components/Todos'

export default {
name: 'app',
        components: {
          Header,
          AddTodo,
          Footer,
          Todos
        },

        data(){
          return {
todos: [
       {
    id: 1,
    title: "Todo One",
    completed: false
       },
       {
    id: 2,
    title: "Todo Two",
    completed: true
       },
       {
    id: 3,
    title: "Todo Three",
    completed: false
       }
]
          } 

        },
        methods: {
        deleteTodoItem(id){
         this.todos =  this.todos.filter(todo => todo.id !== id)
        },
        addTodoItem(newTodo){
          this.todos = [...this.todos,newTodo]
        }
        
        }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
       /* margin-top: 60px; */
       
}
.btn{
padding: 7px 20px;
background:#555;
cursor: pointer;
border: none;
display: inline-block;
color: #fff;
}
.btn:hover{
background: #666;
}
</style>
