<template>
  <div>
    <input type="text" v-model="newTodoItem" />
    <button @click="addTodoItem">Add</button>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data() {
    return {
      newTodoItem: ''
    }
  },
  methods: {
    addTodoItem() {
      this.$emit('addtodoitem', this.newTodoItem)
      this.newTodoItem = ''
    }
  }
})
</script>
