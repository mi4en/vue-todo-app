<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" class="center"/>
    <Header />
    <AddTodo v-on:add-todo="addTodo" />
    <Todos v-bind:todosFromAppVue="todosFromData" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Todos from "./components/Todos";
import AddTodo from "./components/AddTodo";
import Header from "./components/layout/Header";

export default {
  name: "app",
  components: {
    Todos,
    AddTodo,
    Header
  },
  data() {
    return {
      todosFromData: [
        {
          id: 1,
          title: "Todo one",
          completed: false
        },
        {
          id: 2,
          title: "Todo two",
          completed: false
        },
        {
          id: 3,
          title: "Todo three",
          completed: false
        }
      ]
    };
  },
  methods: {
    deleteTodo(id) {
      this.todosFromData = this.todosFromData.filter(value => value.id !== id);
    },
    addTodo(newTodo) {
      this.todosFromData = [...this.todosFromData, newTodo]
    }
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
  margin-left: 100px;
  margin-right: 100px;
}

.center {
  display: block;
  margin-left: auto;
  margin-right: auto;
}

.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover {
  background: #999
}
</style>
