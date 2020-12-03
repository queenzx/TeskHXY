<template>
  <login></login>
</template>

<script>
import login from './components/login/index.vue'

export default {
  name: 'App',
  components: {
    login
  }
}
</script>

<style>
html,body{width:100%;height:100%}
*{
  box-sizing: border-box;
  margin: 0px;
  padding: 0px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100%;
  width: 100%;
}
</style>
