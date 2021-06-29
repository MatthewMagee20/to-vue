<template>
  <div class="container">
    <div class="row p-3">
      <div class="col">
        <TodoForm @new-todo="addTodo($event)" />
      </div>
    </div>
    <div class="row p-3">
      <div class="col">
        <ul id="todo-list">
          <TodoItem
            v-for="(todo, index) in todos"
            :key="index"
            :description="todo.desc"
            :completed="todo.completed"
            @on-toggle="completeTodo(todo)"
            @on-delete="deleteTodo(todo)"
          >
          </TodoItem>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import TodoForm from "./TodoForm.vue";
import TodoItem from "./TodoItem.vue";

export default {
  data() {
    return {
      todos: [
        { desc: "Shopping", completed: false },
        { desc: "Study", completed: false },
        { desc: "Read", completed: true },
      ],
    };
  },
  methods: {
    addTodo(newTodo) {
      this.todos.push({ desc: newTodo });
    },
    deleteTodo(deletedTodo) {
      this.todos = this.todos.filter((todo) => todo !== deletedTodo);
    },
    completeTodo(todo) {
      todo.completed = !todo.completed;
      console.log(todo.completed);
    },
  },
  components: {
    TodoForm,
    TodoItem,
  },
};
</script>

<style>
ul {
  list-style: none;
}

#todo-list {
  padding: 0;
}

ul li span {
  float: right;
}
</style>
