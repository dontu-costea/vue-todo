<template>
  <div class="container">
    <div class="todo__block">
      <div class="todo__title">
        TODOLIST
      </div>
      <div class="todo-input__block">
        <input type="text" class="todo-input">
        <button class="add-todo" type="submit">+</button>
      </div>

      <div class="todo">
        <div class="todo__item">
          <div class="todo-text__block">
            <input type="checkbox" class="todo__checkbox">
            <input type="text" class="todo__text" readonly>
          </div>
          <div class="edit__block">
             <span class="edit">edit</span>
            <button type="submit" class="todo__delete">x</button>
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

<script>

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
.todo-input__block {
  width: 100%;
  margin-top: 15px;
}
.todo__title {
  font-size: 30px;
  color: #4D5D4D;
  font-weight: bold;
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

.todo {
  margin-top: 7px;
  width: 100%;
}
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
