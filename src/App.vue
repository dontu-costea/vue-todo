<template>
  <div class="container">
    <div class="todo__block">
      <div class="todo__title">
        TODOLIST
      </div>
        <add-todo-block @create="addTodo"/>
        <div class="no__todo" v-if="!todos.length">
          TODOLIST is empty
        </div>
        <todo-list :todos="todos" @remove="removeTodo"/>

    </div>
  </div>
</template>

<script>
import AddTodoBlock from "@/components/AddTodoBlock.vue";
import TodoList from "@/components/TodoList.vue"

export default {
  components: {
    AddTodoBlock,
    TodoList
},
  data() {
    return {
      todos: [],
    }
  },
  methods: {
    addTodo(todo) {
      this.todos.push(todo);
    },
    removeTodo(todo) {
      this.todos = this.todos.filter(p => p.id !== todo.id)
    },
    editTodo() {
      
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.container {
  background-color: #489CC1;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100vw;
  height: 100vh;
}
.todo__block {
  width: 30%;
  background-color: #fff;
  border-radius: 4px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 15px 20px;
}
.todo__title {
  font-size: 30px;
  color: #4D5D4D;
  font-weight: bold;
}
.no__todo {
  margin-top: 15px;
  color: #777777;
}
</style>
