<template>
  <div class="todo__item" :class="{itemBackground: todo.checked}">
    <div class="todo-text__block">
      <input type="checkbox" class="todo__checkbox" v-model="todo.checked">
      <input type="text" class="todo__text" :disabled="editable" v-model="todo.todo" :class="{textLine: todo.checked}">
    </div>
    <div class="edit__block">
      <fa icon="fa-regular fa-circle-check" class="edit" @click="editable = !editable" :class="{displayBlock: !editable}"/>
      <fa icon="fa-solid fa-pen" class="edit" @click="editable = !editable" :class="{displayBlock: editable}"/>
      <fa icon="fa-solid fa-xmark" class="todo__delete" @click="$emit('remove', todo)"/>
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
      editable: true
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
  background-color: #F2F8FE;
  transition: 0.3s all ease;
}
.todo__text {
  font-size: 16px;
  line-height: 40px;
  outline: none;
  margin-left: 10px;
  width: 85%;
  border: none;
  color: #618C9B;
  background: none;
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
.edit {
  cursor: pointer;
  color: #D0E4EE;
  transition: 0.3s;
  display: none;
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
.todo__delete:hover, .edit:hover {
  color: #489CC1;
}
.textLine {
  text-decoration: line-through;
}
.itemBackground {
  background-color: #F9FDFF;
}
.displayBlock {
  display: block;
}
</style>