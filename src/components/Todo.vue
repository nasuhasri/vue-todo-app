<!--- for every todo in our list the “Todo” component is used with it’s own unique data -->
<template>
  <!-- only use the class if todo is completed -->
  <div v-bind:class="{ 'completed': todo.completed }">
    <!-- change the todo status -->
    <p v-on:click="markComplete">{{ todo.title }}</p>
  </div>
</template>

<script>
export default {
  name: 'Todo',
  props: [
    "todo"
  ],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed
    }
  }
}
</script>

<style scoped>
  .completed {
    text-decoration: line-through;
  }
</style>