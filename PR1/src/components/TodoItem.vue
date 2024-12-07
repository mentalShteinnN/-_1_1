<template>
  <div
    :class="(completed ? 'green' : 'red') + ' todo_item'"
    @click="changeTodo"
    @dblclick="removeTodo"
  >
    <h2>{{ title }}</h2>
  </div>
</template>
<script>
export default {
  props: ['title', 'id', 'completed'],
  emits: ['changeTodo', 'removeTodo'],
  methods: {
    changeTodo() {
      this.$emit('changeTodo', this.id)
    },
    removeTodo() {
      this.$emit('removeTodo', this.id)
    }
  }
}
</script>
<style scoped>
.green {
  background-color: forestgreen;
}
.red {
  background-color: crimson;
}
</style>
