<template>
  <div class="todo-item">
    <input type="checkbox" v-model="todo.isDone" />
    <p v-if="todo.isDone">
      <s>{{ todo.title }}</s>
    </p>
    <p v-else>
      {{ todo.title }}
    </p>
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
