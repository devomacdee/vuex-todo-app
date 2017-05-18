<template>
  <div id="app" class="container-fluid">
    <completed-todos></completed-todos>
    <get-todo></get-todo>
    <current-todos></current-todos>
  </div>
</template>

<script>
import GetTodo from './components/GetTodo.vue'
import CurrentTodos from './components/CurrentTodos.vue'
import CompletedTodos from './components/CompletedTodos.vue'
export default {
  name: 'app',
  components: {
    GetTodo,
    CurrentTodos,
    CompletedTodos
  }
}
</script>

<style lang="scss">
body {
  padding: 5rem;
  font-family: Helvetica, sans-serif;
}
input {
  margin: 1rem 0;
}

</style>
