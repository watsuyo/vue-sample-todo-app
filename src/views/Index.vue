<template>
  <div>
    <h1>Todoリスト</h1>
    <TodoItemList class="todo-item-list" :todoList="todoList" />
  </div>
</template>

<script>
import TodoItemList from '@/components/TodoItemList.vue'

export default {
  components: {
    TodoItemList
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
  }
}
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
