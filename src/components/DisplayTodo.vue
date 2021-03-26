<template>
  <p :class="isDone ? 'done-class' : ''">{{ todoItem }}</p>
  <button @click="doneItem">Done</button>
  <button @click="emitDeleteItem">Delete</button>
</template>

<script>
export default {
  name: "DisplayTodo",
  props: ["todo"],
  data() {
    return {
      todoItem: this.todo,
      isDone: false,
    };
  },
  methods: {
    doneItem: function () {
      console.log("Done " + this.todoItem);
      this.isDone = true;
    },
    emitDeleteItem: function () {
      this.$emit("emitDeleteItem", this.todoItem);
    },
  },
};
</script>

<style>
.done-class {
  text-decoration: line-through;
}
</style>