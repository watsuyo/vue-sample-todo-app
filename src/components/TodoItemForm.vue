<template>
  <div>
    <input type="text" v-model="todoTitleText" />
    <button @click="addTodoItem">Add</button>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data() {
    return {
      todoTitleText: ''
    }
  },
  methods: {
    addTodoItem() {
      this.$emit('addtodoitem', this.todoTitleText)
      this.todoTitleText = ''
    }
  }
})
</script>
