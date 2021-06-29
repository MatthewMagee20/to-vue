<template>
  <li
    :class="completed ? 'completed' : 'not-complete'"
    @click="$emit('on-toggle')"
    class="todo-item"
  >
    {{ description }}
    <span><i @click="$emit('on-delete')" class="bi bi-x-square"></i></span>
  </li>
</template>

<script>
export default {
  props: { description: String, completed: Boolean },
};
</script>

<style>
.todo-item {
  border: 1px solid black;
  padding: 10px;
}

.completed {
  text-decoration: line-through;
}
</style>
