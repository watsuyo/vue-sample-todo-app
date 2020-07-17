<template>
  <div class="todo-item">
    <div v-if="!editing">
      <input type="checkbox" v-model="todo.isDone" />
      <span :class="[todo.isDone ? 'todo-done' : '']">{{ todo.title }}</span>
      <button @click="editTodo()">編集</button>
      <button @click="deleteTodo(todo.uid)">削除</button>
    </div>
    <div v-if="editing">
      <input type="text" v-model="todo.title" />
      <button @click="saveTodo(todo.uid)">保存</button>
    </div>
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
  data() {
    return {
      editing: false
    }
  },
  methods: {
    deleteTodo(uid: string) {
      this.$emit('deletetodo', uid)
    },
    editTodo() {
      this.editing = true
    },
    saveTodo() {
      this.editing = false
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
