<!--- for every todo in our list the “Todo” component is used with it’s own unique data -->
<template>
  <div>
    <p>{{ todo.title }}</p>
  </div>
</template>

<script>
export default {
  name: 'Todo',
  props: [
    "todo"
  ]
}
</script>

<style scoped>

</style>