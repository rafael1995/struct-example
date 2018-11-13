<template>
  <div id="app">
    <Partida msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import Partida from './views/Partida.vue'

export default {
  name: 'app',
  components: {
    Partida
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
</style>
