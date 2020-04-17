<template>
  <div id="app">
    <h1>Vue Day 2</h1>
    <Accordion title="Click Here to Expand" content="Hello, World! I hide and 
    show based on Vue class binding!" />
    <Accordion title="CWhat is Vue?" content="A popular JavaScript library, used
    for creating dynamic and reactive webpages!" />
    <TodoList />
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue'
import Accordion from './components/Accordion.vue'

export default {
  name: 'App',
  components: {
    TodoList,
    Accordion
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
