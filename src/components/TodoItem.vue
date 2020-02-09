<template>
  <div class="todo-item">
    <span v-if="isUpdateMode">
      <input type="text" v-model="updatedTodo" />
      <button @click="updateTodo">更新</button>
      <button @click="toggleUpdateMode">キャンセル</button>
    </span>

    <span v-else>
      <input type="checkbox" v-model="todo.isDone" />
      <span @click="toggleUpdateMode">
        <span v-if="todo.isDone">
          <s>{{ todo.title }}</s>
        </span>
        <span v-else>
          {{ todo.title }}
        </span>
      </span>
      <span @click="deleteTodo">×</span>
    </span>
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
      isUpdateMode: false,
      updatedTodo: ''
    }
  },

  methods: {
    deleteTodo() {
      this.$emit('deleteTodo', this.todo)
    },

    toggleUpdateMode() {
      this.isUpdateMode = !this.isUpdateMode
    },

    updateTodo() {
      this.todo.title = this.updatedTodo
      this.toggleUpdateMode()
    }
  }
})
</script>

<style scoped lang="scss">
.todo-item {
  display: flex;
}
</style>
