<template>
  <div id="app" class="container">
    <img width="25%" src="./assets/logo.png">
    <todo-input @addTodo="addTodo"></todo-input>
    <todo-list :todoList="todoList"></todo-list>
    <!-- @TODO
    * delete
    * update
    * find-->
  </div>
</template>

<script>
import todoList from "./components/todolist";
import todoInput from "./components/todo-input";

export default {
  name: "App",
  components: {
    todoList,
    todoInput
  },
  data() {
    return {
      todoList: []
    };
  },
  methods: {
    addTodo(todoItem) {
      this.todoList.push(todoItem);
      console.log(this.todoList);
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
