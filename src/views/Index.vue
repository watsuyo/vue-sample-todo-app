<template>
  <div>
    <h1>Todoリスト</h1>
    <TodoItemForm @addtodoitem="addTodoItem($event)"></TodoItemForm>
    <TodoItemList
      class="todo-item-list"
      :todoList="todoList"
      @deletetodo="deleteTodo($event)"
    />
  </div>
</template>

<script lang="ts">
import Vue, { PropType } from 'vue'
import TodoItemList from '@/components/TodoItemList.vue'
import TodoItemForm from '@/components/TodoItemForm.vue'
import { Todo } from '../../types'

export default Vue.extend({
  components: {
    TodoItemList,
    TodoItemForm
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
    addTodoItem(todoTitleText: string) {
      const uid: string = Math.floor(
        Math.random() * 100000000000000000
      ).toString(36)
      const newTodoItem: Todo = {
        uid: uid,
        title: todoTitleText,
        isDone: false,
        createdAt: new Date()
      }
      this.todoList.push(newTodoItem)
    },
    deleteTodo(uid: string) {
      this.todoList = this.todoList.filter(item => item.uid !== uid)
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
