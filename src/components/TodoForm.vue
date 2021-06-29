<template>
  <form @submit.prevent="addTodo()">
    <div class="mb-3">
      <label for="todoInput" class="form-label">Enter Todo</label>
      <input
        v-model="todo_input"
        type="text"
        class="form-control"
        id="todoInput"
        placeholder="Todo...."
      />
    </div>
    <div class="d-grid gap-2">
      <button type="submit" class="btn btn-primary">
        Submit
      </button>
    </div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      todo_input: "",
    };
  },
  methods: {
    addTodo() {
      if (this.todo_input.length > 0) {
        this.$emit("new-todo", this.todo_input);
      }
    },
  },
};
</script>
