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
import axios from 'axios';

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
        
      ]
    };
  },
  methods: {
    deleteTodo(id) {
      axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
        .then(res => this.todosFromData = this.todosFromData.filter(value => value.id !== id))
        .catch(err => console.log(err))
    },
    addTodo(newTodo) {
      const { title, complited } = newTodo;

      axios.post('https://jsonplaceholder.typicode.com/todos', {
        title,
        complited
      })
        .then(res => this.todosFromData = [...this.todosFromData, res.data])
        .catch(err => console.log(err))
      
    }
  },
  created() {
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5')
      .then(res => this.todosFromData = res.data)
      .catch(err => console.log(err));
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
