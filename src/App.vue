<template>
  <div id="app">
    <img id="vue-logo" alt="Vue logo" src="./assets/logo.png" />
    <Header />
    <Todos v-bind:todosFromAppVue="todosFromData" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from './components/Todos';
import Header from './components/layout/Header'

export default {
  name: "app",
  components: {
    Todos,
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
}

#vue-logo {
  align-self: center;
}
</style>
