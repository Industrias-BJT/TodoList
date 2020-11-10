<template>
  <div>
    <div id="header"></div>
    <div id="main-conteiner">
      <h2>Todos</h2>
      <TodosAdd @add-todo="addTodo"/>
      <Todos :todosList="copyTodos" @delate-todo="deleteTodo"/>
    </div>
  </div>
</template> 

<script>
  //import HelloWorld from './components/HelloWorld.vue'
  import Todos from './components/Todos'
  import TodosAdd from './components/TodosAdd'
  export default {
    name: 'App',
    components: {
        // Search,
        Todos,
      TodosAdd
    },
    data(){
      return{
        todos:[
                {
                  id:1,
                  title:'Scold fredy',
                  completed:false
                },
                {
                  id:2,
                  title:'Scold karen',
                  completed:false
                },
                {
                  id:3,
                  title:'Scold me',
                  completed:false
                }
              ],
        copyTodos:[]
      }
    },
    created(){
      this.copyTodos = [...this.todos]
    },
    methods:{
      deleteTodo(id){
        this.todos = this.todos.filter(todo => todo.id != id)
          this.copyTodos = [... this.todos]
      },
      addTodo(todo){
        this.todos.push(todo)
        this.copyTodos=[... this.todos]
      }
    }
  }
</script>

<style>
  *{
    box-sizing: border-box;
  }
  body{
    font-family: Arial, Helvetica, sans-serif;
    font-size: 1.5em;
    padding: 0;
    margin: 0;
  }
  #main-conteiner{
    border:solid 1px #ccc;
    width: 600px;
    margin: 100px auto;
  }
  #header{
    background-color: black;
    padding: 10px;
  }
  h2{
    padding:  0 10px;
  }
</style>
