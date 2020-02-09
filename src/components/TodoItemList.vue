<template>
  <div>
    <div>
      <TodoItem
        v-for="(todo, key) in todoList"
        :key="key"
        :todo="todo"
        @deleteTodo="deleteTodo($event)"
      />
    </div>
  </div>
</template>

<script lang="ts">
import Vue, { PropType } from 'vue'
import TodoItem from '@/components/TodoItem.vue'
import { Todo } from '../../types'

export default Vue.extend({
  components: {
    TodoItem
  },

  props: {
    todoList: {
      type: Array as PropType<Todo[]>,
      required: true
    }
  },

  methods: {
    deleteTodo(todo: Todo) {
      this.$emit('deleteTodo', todo)
    }
  }
})
</script>
