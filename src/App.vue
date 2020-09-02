<template>
  <div id="app">
    <!--<img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <userSignup />
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import userSignup from './components/userSignup'

export default {
  name: 'App',
  components: {
    //HelloWorld
    userSignup
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
