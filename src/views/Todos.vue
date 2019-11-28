<template>
  <div class="todos-container">
    <Loader v-if="isLoading" />
    <div
      v-else
      class="todos-content"
    >
      <div class="add-todo">
        <input 
          class="add-todo-input"
          type="text"
          v-model="text"
        >
        <button 
          class="add-todo-button"
          v-on:click="addTodo"
          v-on:mousedown.prevent
        >
          Add todo
        </button>
      </div>
      <TodoList 
        v-bind:todos="todos" 
        v-on:remove-todo="removeTodo"
      />
    </div>
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
      isLoading: true,
      text: ''
    };
  },
  mounted() {
    fetch("https://jsonplaceholder.typicode.com/todos?_limit=5")
      .then(response => response.json())
      .then(json => {
        setTimeout(() => {
          this.todos = json;
          this.isLoading = false;
        }, 3000);
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
    },
    addTodo() {
      if (!this.text.length) {
        return;
      }

      const todo = {
        id: this.todos.length + 1,
        title: this.text,
        completed: false
      };

      this.todos.push(todo);
      this.text = '';
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

.todos-content {
  box-sizing: border-box;
  padding: 40px 20px;
}

.add-todo {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 20px;
}

.add-todo-input {
  flex-basis: 30%;
  height: 32px;
  margin-right: 15px;
  padding-left: 10px;
  border: 1px solid #3f4d71;
  border-radius: 2px;
  outline: none;
}

.add-todo-input:focus {
  border-color: #55ae95;
}

.add-todo-button {
  flex-basis: 10%;
  height: 36px;
  border: none;
  border-radius: 4px;
  background-color: #3f4d71;
  color: #fff;
}
</style>