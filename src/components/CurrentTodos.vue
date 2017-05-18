<template lang="html">
  <div id="current-todos">
    <h3 v-if="todos.length">Current Todos: {{ todos.length }}</h3>
    <ul class="list-group">
      <li class="list-group-item"
          v-for="todo in todos">
        {{ todo.body }}
        <div class="btn-group">
          <button type="button"
                  class="btn btn-default btn-sm"
                  @click="edit(todo)">
            <span class="glyphicon glyphicon edit"></span>
            Edit
          </button>
          <button type="button"
                  class="btn btn-default btn-sm"
                  @click="complete(todo)">
            <span class="glyphicon glyphicon-ok-circle"></span>
            Complete
          </button>
          <button type="button"
                  class="btn btn-default btn-sm"
                  @click="remove(todo)">
            <span class="glyphicon glyphicon-remove-circle"></span>
            Remove
          </button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  computed: {
    todos () {
      return this.$store.getters.todos
    }
  },
  methods: {
    edit (todo) {
      this.$store.dispatch('editTodo', todo)
    },
    complete (todo) {
      this.$store.dispatch('completeTodo', todo)
    },
    remove (todo) {
      this.$store.dispatch('removeTodo', todo)
    }
  }
}
</script>

<style lang="css">
  .list-group-item {
    display: flex;
    justify-content: space-between;
    width: 100%;
    font-size: 2rem;
  }
</style>
