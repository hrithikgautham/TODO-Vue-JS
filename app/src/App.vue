<template>
  <div id="app">
    <Todos v-bind:todos="todos"></Todos>
  </div>
</template>

<script>
import Todos from './components/Todos';

export default {
  name: 'app',
  components: {
    Todos
  },
  data() {
    return {
      todos: [
        {id: 1, title: "get the trash out", isCompleted: false},
        {id: 2, title: "do laundry", isCompleted: true},
        {id: 3, title: "go wash ur car", isCompleted: false},
        {id: 4, title: "hit the gym", isCompleted: true},
        {id: 5, title: "hahahaha hahahah", isCompleted: false},
      ]
    }
  }
}
</script>

<style scoped>
    #app {
      border: 4px solid black;
      border-radius: 5px;
      box-sizing: border-box;
    }
</style>
