<template>
  <div id="app">
    <Questions/>
  </div>
</template>

<script>
import Questions from './components/Questions'

export default {
  name: 'App',
  components: {
    Questions
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

body {
  margin: 0px;
}
</style>
