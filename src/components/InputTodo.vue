<template>
  <label for="add-todo">To do</label><br />
  <input
    type="text"
    name="add-todo"
    placeholder="Add a task"
    v-model="todoContent"
    @keypress.enter="emitAddTodoItem"
  />
  <button @click="emitAddTodoItem">Add</button>
</template>

<script>
export default {
  name: "InputTodo",
  data() {
    return {
      todoContent: "",
    };
  },
  methods: {
      emitAddTodoItem: function () {
          this.$emit('emitAddTodoItem', this.todoContent);
      }
  }
};
</script>

<style>
</style>