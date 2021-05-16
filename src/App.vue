<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <user-info></user-info>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import UserInfo from './components/UserInfo.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    UserInfo
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
