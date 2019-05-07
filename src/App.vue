<template>
  <div id="app">
    <todo></todo>
  </div>
</template>

<script>
import todo from './components/todo.vue'

export default {
  name: 'app',
  components: {
      todo
  }
}
</script>

<style>
#app {
  width: 100%;
  height: 800px;
  overflow: hidden;
  background-color:lightgray;
  opacity: 0.5;
}
</style>
