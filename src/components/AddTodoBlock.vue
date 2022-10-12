<template>
  <div class="todo-input__block">
    <input type="text" class="todo-input" v-model.trim="todos.todo" @keyup.enter="addTodo">
    <button class="add-todo" type="submit" @click="addTodo">+</button>
  </div>
</template>

<script>


export default {
  data() {
    return {
      todos: {
        todo: ''
      }
    }
  },
  methods: {
    addTodo() {
      if(this.todos.todo) {
        this.todos.id = Date.now();
        this.todos.checked = false;
        this.$emit('create', this.todos);
        this.todos = {
          todo: ""
        }
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
