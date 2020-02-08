<template>
  <div>
    <button @click="addTodo">追加</button>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  methods: {
    addTodo() {
      this.$emit('addTodo')
    }
  }
})
</script>

<style lang="scss" scoped></style>
