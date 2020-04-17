<template>
  <section>
    <h2>To-Do List</h2>
    <ul>
   <Todo v-for="todo in todos" :key="todo.task" :todo="todo" 
   v-on:complete-todo="completeTodo" />
    </ul>
  </section>
</template>

<script>
import Todo from './ToDo.vue';

export default {
    name: 'TodoList',
    components: {
        Todo
    },
    data () {
      return {
        todos: [
            {
                task: 'Buy Milk',
                completed: false
            },
             {
                task: 'Pick up Prescription',
                completed: true
            },
             {
                task: 'Study Vue',
                completed: false
            },
             {
                task: 'Install Visual Studio Code',
                completed: false
            },
        ]
      }
    },
    methods: {
       completeTodo ( todo ) {
           const todoIndex = this.todos.indexOf( todo );
           this.todos[todoIndex].completed = true ;
       }
    }
}
</script>
   
<style>

</style>