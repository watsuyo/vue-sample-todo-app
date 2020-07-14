<template>
  <div>
    <h1>Todoリスト</h1>
    <TodoItemForm @addtodoitem="addTodoItem($event)"></TodoItemForm>
    <TodoItemList class="todo-item-list" :todoList="todoList" />
  </div>
</template>

<script>
import TodoItemList from '@/components/TodoItemList.vue'
import TodoItemForm from '@/components/TodoItemForm.vue'

export default {
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
    addTodoItem(todoItem) {
      const newTodoItem = {
        uid: 'bp0m4jl4a08',
        title: todoItem,
        isDone: false,
        createdAt: new Date()
      }
      this.todoList.push(newTodoItem)
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
