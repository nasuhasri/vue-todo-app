<!--- a container where all todos should be displayed -->
<template>
  <div>
    <h2>My todolist</h2>
    <ul>
      <!-- when looping must add unique key to every item -->
      <li v-bind:key="todo.id" v-for="todo in todos">
        <!-- pass the current todo object to the Todo component -->
        <Todo v-bind:todo="todo" />
      </li>
    </ul>
  </div>
</template>

<script>
import Todo from './Todo.vue';
import AddTodo from './AddTodo.vue';

export default {
  name: 'Todos',
  components: {
    Todo,
    AddTodo
  },
  // added props from app.vue <Todos v-bind:todos="todos" />
  props: [
    "todos"
  ]
}
</script>

<style scoped>

</style>
