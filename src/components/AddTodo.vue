<template>
  <div>
    <form @submit="addTodo">
      <input type="text" v-model="title" name="title">
      <button type="submit">Add</button>
    </form>
  </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';

export default {
  name: 'AddTodo',
  // two-way binding
  data() {
    return {
      // as soon as we make a change to our input the “title” in our data is also updated - allow us to use value of "title" when want to add todos
      title: ''
    }
  },
  methods: {
    addTodo(e) {
      // prevent form from submit to a file
      e.preventDefault();

      const newTodoObj = {
        id: uuidv4(),
        title: this.title,
        completed: false
      }

      this.$emit('add-todo', newTodoObj);
      this.title = '';
    }
  }  
}
</script>

<style scoped>

</style>