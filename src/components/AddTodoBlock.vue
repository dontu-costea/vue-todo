<template>
  <div class="todo-input__block">
    <input type="text" class="todo-input" v-bind:value="todo.emptyTodo" @input="todo.emptyTodo = $event.target.value">
    <button class="add-todo" type="submit">+</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todo: {
        emptyTodo: ''
      }
    }
  }
}
</script>

<style scoped>
.todo-input__block {
  width: 100%;
  margin-top: 15px;
}
.todo-input {
  font-size: 20px;
  line-height: 35px;
  width: 79%;
  outline: none;
  text-align: center;
  font-style: italic;
  color: #489CC1;
}
.add-todo {
  width: 19%;
  font-size: 20px;
  line-height: 35px;
  font-weight: bold;
  float: right;
  cursor: pointer;
  color: white;
  background-color: #489CC1;
  border: 1px solid #489CC1;
  transition: 0.3s;
}
.add-todo:hover {
  background-color: #397B98;
}
</style>
