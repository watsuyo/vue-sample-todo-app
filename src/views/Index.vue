<template>
  <div>
    <h1>Todoリスト</h1>
    <InputTodo @addTodo="addTodo($event)" />
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

interface Data {
  uid: string
  title: string
  isDone: boolean
  createdAt: Date | null
}

export default Vue.extend({
  components: {
    TodoItemList,
    InputTodo
  },

  data() {
    return {
      todoList: [
        {
          uid: 'bp0m4jl4a08',
          title: '7時に起きる',
          isDone: false,
          createdAt: new Date()
        }
      ]
    }
  },

  methods: {
    addTodo(newTodo: string) {
      this.todoList.push({
        uid: Math.floor(Math.random() * 100000000000000000).toString(36),
        title: newTodo,
        isDone: false,
        createdAt: new Date()
      })
    },

    deleteTodo(selectedTodo: Todo) {
      this.todoList = this.todoList.filter(
        todo => todo.uid !== selectedTodo.uid
      )
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
