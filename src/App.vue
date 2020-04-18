<template>
  <div id="app">
    <Header />
    <AddTodo />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
    <Constructor />
    <BuildingList />
  </div>
</template>

<script>
  import Header from './components/layout/Header'
  import Todos from './components/Todos'
  import AddTodo from './components/AddTodo'
  import Constructor from './components/satisfactory/Constructor'
  import BuildingList from './components/satisfactory/BuildingList'


  export default {

    name: 'App',

    components: {
      Header,
      Todos,
      AddTodo,
      Constructor,
      BuildingList
    },

    data() {
      return {
        todos: [
          {
            id: 1, 
            title: "Todo numero uno",
            completed: false
          },
          {
            id: 2, 
            title: "Todo numero dos",
            completed: true
          },
          {
            id: 3,
            title: "Todo numero tres",
            completed: false
          }
        ]
      }
    },
    methods: {
      deleteTodo(id) {
        this.todos = this.todos.filter(todo => todo.id !== id);
      }
    }
  }
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    font-family: Arial, Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }

  .btn {
    display: inline-block;
    border: none;
    background: #666;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }

  .btn:hover {
    background: #777;
    padding: 7px 40px;
  }

/* Default Code
  #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}*/
</style>
