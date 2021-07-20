<template>
  <h1>This is Body Component</h1>
  <InputTodo @emitAddTodoItem="addTodoItem"></InputTodo>
  <div v-for="todoItem in todoList" :key="todoItem">
    <DisplayTodo :todo="todoItem" @emitDeleteItem="deleteItem"></DisplayTodo>
  </div>
</template>

<script>
import InputTodo from "./InputTodo.vue";
import DisplayTodo from "./DisplayTodo.vue";

export default {
  components: { InputTodo, DisplayTodo },
  name: "AppBody",
  data() {
    return {
      todoList: [],
    };
  },
  methods: {
    addTodoItem: function (todoItem) {
      this.todoList.push(todoItem);
      console.log(this.todoList);
    },
    deleteItem: function (todoItem) {
      let index = this.todoList.indexOf(todoItem);
      console.log(this.todoList);
      console.log(index, todoItem);
      this.todoList.splice(index, 1);
      console.log(this.todoList);
    },
  },
};
</script>

<style>
</style>