<template>
  <section class="input_elem">
    <input @keydown.enter="addNewTodo" v-model="inputText" />
  </section>
</template>
<script>
export default {
  data() {
    return {
      inputText: ''
    }
  },
  emits: ['addNewTodo'],
  methods: {
    addNewTodo() {
      console.log(this.inputText)
      this.$emit('addNewTodo', this.inputText)
    }
  }
}
</script>
<style scoped></style>
