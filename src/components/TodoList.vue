<template lang="html">
  <div>
    <p>Completed tasks: {{todos.filter(todo => todo.done === true).length}}</p>
    <p>Pending tasks: {{todos.filter(todo => todo.done === false).length}}</p>
    <Todo
      v-on:delete-todo="deleteTodo"
      v-for="todo in todos"
      v-bind:todo="todo"
      :key="todo.id"
    />
  </div>
</template>

<script type="text/javascript">
import Todo from './Todo';

export default {
  props: ['todos'],
  components: {
    Todo,
  },
  methods: {
    deleteTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos.splice(todoIndex, 1);
    },
  },
};
</script>

<style lang="css">
</style>
