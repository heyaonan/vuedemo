<template>
  <div id="app">
   <Login></Login>
   <ParentDom></ParentDom>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Login from './components/ComLogin'
import ParentDom from './components/ParentDom'
export default {
  name: 'app',
  components: {
    Login,
    ParentDom
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
  margin-top: 60px;
}
</style>
