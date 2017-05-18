<template lang="html">
  <div id="get-todo">
    <input type="text"
           class="form-control"
           @change="getTodo"
           placeholder="I need to do...">
    <button class="btn btn-primary"
            @click="addTodo">
      Add
    </button>
  </div>
</template>

<script>
export default {
  computed: {
    newTodo () {
      return this.$store.getters.newTodo
    }
  },
  methods: {
    getTodo (e) {
      this.$store.dispatch('getTodo', e.target.value)
    },
    addTodo () {
      this.$store.dispatch('addTodo')
      this.$store.dispatch('clearTodo')
    }
  }
}
</script>

<style lang="css">
</style>
