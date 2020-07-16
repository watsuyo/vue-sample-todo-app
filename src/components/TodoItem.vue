<template>
  <div class="todo-item">
    <input type="checkbox" v-model="todo.isDone" />
    <span :class="[todo.isDone ? 'todo-done' : '']">{{ todo.title }}</span>
    <button @click="deleteTodo(todo.uid)">削除</button>
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
    deleteTodo(uid: string) {
      this.$emit('deletetodo', uid)
    }
  }
})
</script>

<style scoped lang="scss">
.todo-item {
  display: flex;
}
.todo-done {
  text-decoration: line-through;
}
</style>
