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
    addTodoItem(todoTitleText) {
      const uid = Math.floor(Math.random() * 100000000000000000).toString(36)
      const newTodoItem = {
        uid: uid,
        title: todoTitleText,
        isDone: false,
        createdAt: new Date()
      }
      this.todoList.push(newTodoItem)
    },
    deleteTodo(uid) {
      this.todoList = this.todoList.filter(item => item.uid !== uid)
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
