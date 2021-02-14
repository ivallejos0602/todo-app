<template>
  <div id="app">
    <TareasList></TareasList>
  </div>
</template>

<script>
import TareasList from './components/TareasList.vue'

export default {
  name: 'App',
  components: {
    TareasList
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
