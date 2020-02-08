<template>
  <div>
    <h1>Todoリスト</h1>
    <InputTodo @addTodo="addTodo($event)"></InputTodo>
    <TodoItemList
      class="todo-item-list"
      :todoList="todoList"
      @deleteTodo="deleteTodo($event)"
    />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import InputTodo from '@/components/InputTodo.vue'
import TodoItemList from '@/components/TodoItemList.vue'
import { Todo } from '../../types'

export default Vue.extend({
  components: {
    TodoItemList,
    InputTodo
  },

  data() {
    return {
      todoList: [
        {
          id: 1,
          title: '7時に起きる',
          isDone: false
        }
      ]
    }
  },

  methods: {
    addTodo(newTodo: string) {
      const newIndex = this.todoList.length + 1
      this.todoList.push({ id: newIndex, title: newTodo, isDone: false })
    },

    deleteTodo(selectedTodo: Todo) {
      this.todoList = this.todoList.filter(todo => todo.id !== selectedTodo.id)
    }
  }
})
</script>

<style scoped lang="scss">
.todo-item-list {
  display: -webkit-flex;
  -webkit-justify-content: center;
  justify-content: center;
  -webkit-align-items: stretch;
  align-items: stretch;
  text-align: center;
}
</style>
