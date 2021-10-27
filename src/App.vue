<template>
  <div id="app">
    <h1>Дерево файлов</h1>
    <directory-tree
    />
  </div>
</template>

<script>
import DirectoryTree from './components/DirectoryTree.vue'
export default {
  components: { DirectoryTree },
  name: 'App',
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
ul, li {
  list-style-type: none;
}
</style>
