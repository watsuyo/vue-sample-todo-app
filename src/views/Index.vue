<template>
  <div>
    <h1>Todoリスト</h1>
    <input type="text" v-model="newTitle" placeholder="ToDoを入力" />
    <button v-on:click="addTodo">追加</button>
    <TodoItemList class="todo-item-list" :todoList="todoList" />
  </div>
</template>

<script>
import TodoItemList from '@/components/TodoItemList.vue'

export default {
  components: {
    TodoItemList
  },
  methods: {
    addTodo: function() {
      this.todoList.push({
        uid: this.getUniqueStr(),
        title: this.newTitle,
        isDone: false,
        createdAt: new Date()
      })
      this.newTitle = ''
    },
    getUniqueStr: function() {
      return (
        new Date().getTime().toString(16) +
        Math.floor(1000 * Math.random()).toString(16)
      )
    }
  },
  data() {
    return {
      newTitle: '',
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
