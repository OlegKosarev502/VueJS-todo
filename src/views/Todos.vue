<template>
  <div class="todos-container">
    <Loader v-if="isLoading" />
    <TodoList 
      v-else 
      v-bind:todos="todos" 
      v-on:remove-todo="removeTodo"
    />
  </div>
</template>

<script>
import TodoList from "../components/TodoList";
import Loader from "../components/Loader";

export default {
  name: "todos-container",
  data() {
    return {
      todos: [],
      isLoading: true
    };
  },
  mounted() {
    fetch("https://jsonplaceholder.typicode.com/todos?_limit=5")
      .then(response => response.json())
      .then(json => {
        setTimeout(
          () => {
            this.todos = json;
            this.isLoading = false;
          }, 
          3000
        );
      });
  },
  components: {
    TodoList,
    Loader
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter(todo => {
        return todo.id !== id;
      });
    }
  }
};
</script>

<style scoped>
.todos-container {
  min-height: 85vh;
}

.loader-container {
  height: 85vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>