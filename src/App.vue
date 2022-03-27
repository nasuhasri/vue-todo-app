<template>
  <div id="app">
    <!-- passing the todos to the component as properties but we refer this as props -->
    <!-- passed down the todos as "todos" and use the "todos" as props in Todos.vue -->
    <Todos v-bind:todos="todos" />
    
    <!-- define events; it says on the add-todo event call the addTodo function which define in script tag -->
    <AddTodo v-on:add-todo="addTodo" />
  </div>
</template>

<script>
import Todos from './components/Todos.vue';
import AddTodo from './components/AddTodo.vue';

export default {
  name: 'App',
  components: {
    Todos,
    AddTodo
  },
  // store data in Vue components
  data() {
    return {
      todos: [
        {
          id: 1,
          title: 'Go workout',
          completed: false
        },
        {
          id: 2,
          title: 'Do laundry',
          completed: false
        },
        {
          id: 3,
          title: 'Cook food',
          completed: false
        },
        {
          id: 4,
          title: 'Clean up room',
          completed: false
        },
        {
          i: 5,
          title: 'Finish work',
          completed: false
        }
      ]
    }
  },
  methods: {
    // takes a new todo object
    addTodo(newTodoObj) {
      // add it to the todos array using spread operator
      // spread(...) operator - copy current todos array and add new todo object to it
      this.todos = [...this.todos, newTodoObj];
    }
  }
}
</script>

<style>
</style>
