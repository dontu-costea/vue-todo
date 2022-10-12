<template>
  <div class="todo">
    <todo-item v-for="todo in todos" :todo="todo"  :key="todo.id" @remove="$emit('remove', todo)"/>
  </div>
</template>

<script>
import TodoItem from "@/components/TodoItem.vue"
export default {
  components: {
    TodoItem
  },
  props: {
    todos: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>
.todo {
  margin-top: 7px;
  width: 100%;
}
</style>
