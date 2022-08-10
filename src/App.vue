<template>
  <div class="container">
    <div class="todo__block">
      <div class="todo__title">
        TODOLIST
      </div>
        <add-todo-block/>
        <todo-list :todos="todos"/>

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
      todos: [
        {id: 1, todo:'123'},
        {id: 2, todo:'456'}
      ],
      emptyTodo: '',
      readonly: true,
    }
  },
  methods: {
    addTodo() {
      const newTodo = {
        id: Date.now(),
        todo: this.emptyTodo,
      }
      this.todos.push(newTodo);
      this.emptyTodo = '';
    },
    editTodo() {
      this.readonly = !this.readonly
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
</style>
