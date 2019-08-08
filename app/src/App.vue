<template>
  <div id="app">
    <Header/>
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-on:del-todo="deleteTodo" v-bind:todos="todos"/>
  </div>
</template>

<script>
import Todos from './components/Todos';
import Header from "./components/Header";
import AddTodo from "./components/AddTodo";

export default {
  name: 'app',
  components: {
    Todos,
    Header,
    AddTodo
  },
  data() {
    return {
      todos: []
    }
  },
  methods: {
    deleteTodo(id) {
      fetch('https://jsonplaceholder.typicode.com/todos' + '/' + id, {
        method: "DELETE"
      })
      .then(data => data.json())
      .then(data => this.todos = this.todos.filter(todo => todo.id != id))
      .catch(err => console.error(err));
    },
    addTodo({ title, completed }) {
      // newTodo.id = this.todos.length != 0 ? this.todos[this.todos.length-1].id+1 : 1;
      const obj = {
        title, 
        completed
      };
      fetch('https://jsonplaceholder.typicode.com/todos', {
        method: "POST",
        body: JSON.stringify(obj),
        headers: {
          'Content-Type': 'application/json'
        }
      })
      .then(data => data.json())
      .then(data => this.todos = [...this.todos, data])
      .catch(err => console.log(err));
    }
  },
  created() {
    fetch('https://jsonplaceholder.typicode.com/todos')
    .then(data => data.json())
    .then(data => this.todos = data.slice(0, 5))
    .catch(err => console.error(err));
  }
}
</script>

<style scoped>
    #app {
      border: 4px solid black;
      border-radius: 5px;
    }
</style>
