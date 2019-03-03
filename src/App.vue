<template>
  <div id="app">
    <Header/>
    <TodoContent/>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import TodoContent from './components/TodoContent.vue';

export default {
  name: 'app',
  components: {
    Header,
    TodoContent
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
