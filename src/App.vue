<template>
  <div id="app">
    <h1>Cat Size</h1>
    <Cat></Cat>
  </div>
</template>

<script>
import Cat from './components/Cat'

export default {
  name: 'App',
  components: {
    Cat
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
