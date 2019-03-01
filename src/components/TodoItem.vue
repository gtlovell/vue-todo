<template>
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
    <p>
      <input type="checkbox" v-on:change="markComplete">
      {{todo.title}}
      <button @click="$emit('del-todo', todo.id)" class="del">
        <i class="far fa-trash-alt"></i>
      </button>
    </p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    }
  }
};
</script>

<style scoped>
.todo-item {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px dotted #ccc;
}

.todo-item:hover {
  background: #e4e4e4;
}

.is-complete {
  text-decoration: line-through;
}

.del {
  background: #ff0000;
  color: #fff;
  font-size: 12px;
  border: none;
  padding: 8px 10px;
  border-radius: 50%;
  cursor: pointer;
  float: right;
}

.del:hover {
  background: #b50000;
  cursor: pointer;
}
</style>

