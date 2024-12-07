<template>
  <section>
    <todo-item
      v-for="todo in todos"
      :key="todo.id"
      :title="todo.title"
      :id="todo.id"
      :completed="todo.completed"
      @changeTodo="changeTodo"
      @removeTodo="removeTodo"
    ></todo-item>
  </section>
</template>
<script>
import TodoItem from './TodoItem.vue'
export default {
  components: {
    TodoItem
  },
  props: ['todos'],
  emits: ['changeTodo', 'removeTodo'],
  methods: {
    changeTodo(id) {
      this.$emit('changeTodo', id)
    },
    removeTodo(id) {
      this.$emit('removeTodo', id)
    }
  }
}
</script>
<style scoped></style>
