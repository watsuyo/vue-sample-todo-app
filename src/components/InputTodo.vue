<template>
  <div>
    <input type="text" v-model="newTodo" />
    <AddButton @addTodo="addTodo" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import AddButton from '../components/AddButton.vue'

export default Vue.extend({
  components: {
    AddButton
  },

  data() {
    return {
      newTodo: ''
    }
  },

  methods: {
    addTodo(newTodo: string) {
      this.$emit('addTodo', this.newTodo)
    }
  }
})
</script>

<style lang="scss" scoped></style>
