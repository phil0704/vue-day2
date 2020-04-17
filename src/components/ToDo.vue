<template>
<li v-if="!todo.completed">
    <input type="checkbox" v-on:click="completeTodo( todo )" >
  {{ todo.task }}
</li>
</template>

<script>
  export default {
      name: 'Todo',
      props: [
          'todo'
      ],
      methods: {
          completeTodo ( todo ) {
            this.$emit( 'complete-todo', todo );
          }
      }
  }

</script>

<style>

</style>