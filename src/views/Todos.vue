<template>
  <div id="app">
    <TodoList 
      v-bind:todos="todos"
    />
  </div>
</template>

<script>
import TodoList from '../components/TodoList';

export default {
  name: 'app',
  data() {
    return {
      todos: []
    }
  },
  mounted() {
    fetch('https://jsonplaceholder.typicode.com/todos?_limit=5')
      .then(response => response.json())
      .then(json => { this.todos = json });
  },
  components: {
    TodoList
  }
}
</script>