<template>
  <div id="app">
    <img id="vue-logo" alt="Vue logo" src="./assets/logo.png" />
    <Todos v-bind:todos="todosFromAppVue"/>
  </div>
</template>

<script>
import Todos from './components/Todos';

export default {
  name: "app",
  components: {
    Todos
  },
  data() {
    return {
      todosFromAppVue: [
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
