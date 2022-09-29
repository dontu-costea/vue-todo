<template>
  <div class="todo__item">
    <div class="todo-text__block">
      <input type="checkbox" class="todo__checkbox">
      <input type="text" class="todo__text" disabled :value="todo.todo">
    </div>
    <div class="edit__block">
      <button class="edit" @click= "todo.disabled = !todo.disabled">edit</button>
      <button type="submit" class="todo__delete" @click="$emit('remove', todo)">x</button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    todo: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      
    }
  }
}
</script>

<style scoped>
.todo__item {
  display: flex;
  justify-content: space-between;
  border-top: 0.5px solid grey;
  border-bottom: 0.5px solid grey;
  padding: 0px 5px;
}
.todo__text {
  font-size: 16px;
  line-height: 40px;
  outline: none;
  margin-left: 10px;
  width: 85%;
  border: none;
  color: #618C9B;
}
.todo__checkbox {
  width: 20px;
  height: 15px;
}
.todo-text__block {
  width: 85%;
}
.edit__block {
  display: flex;
  justify-content: center;
  align-items: center;
  justify-content: space-between;
  width: 50px;
}
.todo__delete {
  background: none;
  border: none;
  color: #D0E4EE;
  font-weight: bold;
  font-size: 26px;
  cursor: pointer;
  transition: 0.3s;
}
.todo__delete:hover {
  color: #489CC1;
}
</style>