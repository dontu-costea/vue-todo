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
        <div class="state__block" v-if="todos.length">
          <div class="state"> {{ this.todos.filter(check => check.checked === true).length }} of {{ todos.length }} tasks done</div>
          <button type="submit" class="remove__checked" @click="removeAllChecked(this.todos)">Remove checked <fa icon="fa-solid fa-xmark"/></button>
        </div>
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
      checkboxes: []
    }
  },
  methods: {
    addTodo(todo) {
      this.todos.push(todo);
    },
    removeTodo(todo) {
      this.todos = this.todos.filter(p => p.id !== todo.id)
    },
    removeAllChecked(arr) {
      for (let i = 0; i < arr.length; i++) {
        arr[i].checked = false
      }
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

.state__block {
  display: flex;
  justify-content: space-between;
  width: 100%;
  margin-top: 15px;
}
.state {
  border: 1px solid rgb(158, 154, 154);
  width: 40%;
  font-size: 16px;
  line-height: 30px;
  text-align: center;
}
.remove__checked {
  cursor: pointer;
  color: white;
  background-color: #489CC1;
  border: 1px solid #489CC1;
  transition: 0.3s;
  font-size: 14px;
  widows: 30%;
  padding: 0px 7px;
}
.remove__checked:hover {
  background-color: #397B98;
}
</style>
