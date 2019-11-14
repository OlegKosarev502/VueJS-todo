<template>
  <li class="todo">
    {{ todo.title }}
  </li>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
  .todo {
    font-size: 18px;
    height: 60px;
    margin-bottom: 15px;
    background-color: #fff;
    box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.12);
    border-radius: 5px;
  }

  .todo:hover {
    box-shadow: 0px 0px 4px rgba(0, 0, 0, 0.12), 0px 4px 4px rgba(0, 0, 0, 0.065)
  }
</style>