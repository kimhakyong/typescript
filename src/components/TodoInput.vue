<template>
  <div>
    <label for="todo-input">오늘 할 일:</label>
    <input type="text" id="todo-input" :value="item" @input="handleInput" />
    <button @click="addTodo" type="button">add</button>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  props: {
    item: {
      type: String,
      required: true
    }
  },
  methods: {
    addTodo() {
      this.$emit('add')
    },
    handleInput(event: InputEvent) {
      const eventTarget = event.target as HTMLInputElement
      this.$emit('input', eventTarget.value)
    }
  }
})
</script>

<style scoped></style>
