<template>
  <div>
    <h1>Todoリスト</h1>
    <InputTodo @addTodo="addTodo($event)"></InputTodo>
    <TodoItemList class="todo-item-list" :todoList="todoList" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import InputTodo from '@/components/InputTodo.vue'
import TodoItemList from '@/components/TodoItemList.vue'

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
      console.log(newTodo)
      const newIndex = this.todoList.length + 1
      console.log({ id: newIndex, title: newTodo, isDone: false })
      this.todoList.push({ id: newIndex, title: newTodo, isDone: false })
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
