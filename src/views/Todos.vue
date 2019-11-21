<template>
  <div class="todos-container">
    <Loader v-if="isLoading" />
    <TodoList
      v-else
      v-bind:todos="todos"
    />
  </div>
</template>

<script>
import TodoList from '../components/TodoList';
import Loader from '../components/Loader';

export default {
  name: 'todos-container',
  data() {
    return {
      todos: [],
      isLoading: true
    }
  },
  mounted() {
    fetch('https://jsonplaceholder.typicode.com/todos?_limit=5')
      .then(response => response.json())
      .then(json => {
        setTimeout(() => {
          this.todos = json;
          this.isLoading = false;
        }, 10000);
      });
  },
  components: {
    TodoList,
    Loader
  }
}
</script>

<style scoped>
  .todos-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100%;
  }
</style>