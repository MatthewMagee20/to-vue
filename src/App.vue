<template>
  <Navbar />
  <TodoList />
</template>

<script>
import Navbar from "./components/Navbar.vue";
import TodoList from "./components/TodoList";

export default {
  name: "App",
  components: {
    Navbar,
    TodoList,
  },
};
</script>
