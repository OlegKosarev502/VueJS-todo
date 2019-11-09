<template>
  <div id="app">
    <TodoList 
      v-bind:todos="todos"
    />
  </div>
</template>

<script>
import TodoList from './components/TodoList';

export default {
  name: 'app',
  data() {
    return {
      todos: [
        { id: 1, title: 'First item', isCompleted: false },
        { id: 2, title: 'Second item', isCompleted: false },
        { id: 3, title: 'Third item', isCompleted: false },
      ]
    }
  },
  components: {
    TodoList
  }
}
</script>

<style>
#app { }
</style>
