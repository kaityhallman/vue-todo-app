<template>
  <div id="app">
    <TodoList v-bind:todos="todos" />
    <CreateTodo v-on:add-todo="addTodo" />
  </div>
</template>

<script>

import CreateTodo from './components/CreateTodo';
import TodoList from './components/TodoList';

export default {
  name: 'App',
  components: {
    TodoList,
    CreateTodo,
  },
  data() {
    return {
      todos: [
        {
          title: 'Todo A',
          project: 'Project A',
          done: false,
          id: 1,
        },
        {
          title: 'Todo B',
          project: 'Project B',
          done: true,
          id: 2,
        },
        {
          title: 'Todo C',
          project: 'Project C',
          done: false,
          id: 3,
        },
        {
          title: 'Todo D',
          project: 'Project D',
          done: false,
          id: 4,
        },
      ],
    };
  },
  methods: {
    addTodo(title) {
      this.todos.push({
        title,
        done: false,
      });
    },
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
