<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" class="center"/>
    <Header />
    <router-view/>
  </div>
</template>

<script>
import Header from "./components/layout/Header";

export default {
  name: 'app',
  components: {
    Header
  }
}
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
