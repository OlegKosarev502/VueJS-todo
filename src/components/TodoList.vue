<template>
  <div>
    <ul>
      <TodoItem 
        v-for="todo in todos"
        v-bind:todo="todo"
        v-bind:key="todo.key"
      />
    </ul>
  </div>
</template>

<script>
import TodoItem from './TodoItem';

export default {
  props: ['todos'],
  components: {
    TodoItem
  }
}
</script>