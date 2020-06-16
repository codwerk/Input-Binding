<template>
  <div id="app">
    <add-blog></add-blog>
  </div>
</template>

<script>
import addBlog from './components/addBlog'

export default {
  name: 'App',
  components: {
    'add-blog': addBlog
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
