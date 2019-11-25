<template>
  <div class="todos">
    <div class="todos-list">
      <TodoItem 
        v-for="todo in todos" 
        v-bind:todo="todo" 
        v-bind:key="todo.key"
        v-on:remove-todo="removeTodo"
      />
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem";

export default {
  props: ["todos"],
  components: {
    TodoItem
  },
  methods: {
    removeTodo(id) {
      this.$emit('remove-todo', id);
    }
  }
};
</script>

<style scoped>
.todos {
  box-sizing: border-box;
  padding: 40px 20px;
}
</style>