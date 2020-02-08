<template>
  <div class="todo-item">
    <p>{{ todo.id }}:</p>
    <p>{{ todo.title }}</p>
    <p>{{ todo.isDone }}</p>
    <p @click="deleteTodo">×</p>
  </div>
</template>

<script lang="ts">
import Vue, { PropType } from 'vue'
import { Todo } from '../../types'

export default Vue.extend({
  props: {
    todo: {
      type: Object as PropType<Todo>,
      required: true
    }
  },

  methods: {
    deleteTodo() {
      this.$emit('deleteTodo', this.todo)
    }
  }
})
</script>

<style scoped lang="scss">
.todo-item {
  display: flex;
}
</style>
