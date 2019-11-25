<template>
  <div class="todo">
    <div 
      class="todo-label"
      v-bind:class="{done: todo.completed}"
    >
      {{ todo.title }}
    </div>
    <div class="controls">
      <div 
        class="controls-done"
        v-on:click="todo.completed = !todo.completed"
      >
        Done
      </div>
      <div 
        class="controls-remove"
        v-on:click="$emit('remove-todo', todo.id)"
      >
        Remove
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true
    }
  }
};
</script>

<style scoped>
.todo {
  display: flex;
  justify-content: space-between;
  align-items: center;

  height: 60px;
  padding: 0px 20px;
  margin-bottom: 15px;
  border-radius: 5px;

  font-size: 18px;
  background-color: #fff;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.12);
}

.todo:hover {
  box-shadow: 0px 0px 4px rgba(0, 0, 0, 0.12), 0px 4px 4px rgba(0, 0, 0, 0.065);
}

.controls-done,
.controls-remove {
  display: inline-block;
  padding: 4px 10px;
  border-radius: 4px;
  transition: all 0.5s;
  color: #fff;
  cursor: pointer;
}

.controls-done {
  background-color: #55ae95;
}

.controls-done:hover {
  background-color: #3f4d71;
}

.controls-remove {
  margin-left: 10px;
  background-color: #ffac8e;
}

.controls-remove:hover {
  background-color: #fd7792;
}

.done {
  text-decoration: line-through;
}
</style>