<template>
  <div id="app">
    <login></login>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Login from './components/login/Login.vue'

export default {
  name: 'app',
  components: {
    Login
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
html,body{ height: 100%;}
body { height: 100%; padding: 0; margin: 0; }
</style>
