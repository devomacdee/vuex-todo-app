<template lang="html">
  <div id="completed-todos">
    <h3 v-if="completed.length">Completed Todos: {{ completed.length }}</h3>
    <ul class="list-group">
      <li class="list-group-item"
          v-for="todo in completed">
          {{ todo.body }}
          <button type="button"
                  class="btn btn-default btn-sm"
                  @click="remove(todo)">
            <span class="glyphicon glyphicon-remove-circle"></span>
            Remove
          </button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  computed: {
    completed () {
      return this.$store.getters.completedTodos
    }
  },
  methods: {
    removeTodo (todo) {
      this.$store.dispatch('removeTodo', todo)
    }
  }
}
</script>

<style lang="css">
</style>
