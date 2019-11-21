<template>
  <div class="todos">
    <ul class="todos-list">
      <TodoItem 
        v-for="todo in todos" 
        v-bind:todo="todo" 
        v-bind:key="todo.key" 
      />
    </ul>
  </div>
</template>

<script>
import TodoItem from "./TodoItem";

export default {
  props: ["todos"],
  components: {
    TodoItem
  }
};
</script>

<style scoped>
.todos {
  box-sizing: border-box;
  padding: 40px 20px;
}
.todos-list {
  margin: 0;
  padding: 0;
  list-style: none;
}
</style>