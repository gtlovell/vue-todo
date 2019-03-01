<template>
  <div class="list">
    <div v-bind:key="todo.id" v-for="todo in todos">
      <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)"/>
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem";

export default {
  name: "Todos",
  components: {
    TodoItem
  },
  props: ["todos"]
};
</script>

<style scoped>
.list {
  width: 30%;
  box-shadow: 0 8px 6px -6px rgb(181, 181, 181);
  margin: 0 auto;
}
</style>
