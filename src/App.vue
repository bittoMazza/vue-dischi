<template>
  <div id="app">
    <Header/>
    <Main/>
  </div>
</template>

<script>

import Header from "./components/Header.vue"
import Main from "./components/Main.vue"
export default {
  name: 'App',
  components: {
    Header,
    Main,
  }
}
</script>

<style lang="scss">
@import "~bootstrap-icons/font/bootstrap-icons.css"; 
@import "~bootstrap/scss/bootstrap.scss";
@import "./styles/variables.scss";
body{
  background-color: $mainColor;
}
</style>
