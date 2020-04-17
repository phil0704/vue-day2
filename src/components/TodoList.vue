<template>
  <section>
    <h2>To-Do List</h2>
    <form @submit="addTodo">
        <label for="new-todo">
            Add a New To-Do:
            <input type="text" name="new-todo" v-model="newTodo"> 
        </label>
            <input type="submit" value="Submit"> 
    </form>
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
        newTodo: '', 
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
           this.todos[todoIndex].completed = true;
       },
       addTodo ( event ) {
           event.preventDefault(); // Stop this form from refreshing the page!
           const newTodo = this.newTodo;
           this.todos.push( {
               task: newTodo,
               completed: false
           } );
           this.newTodo = ''; // Clear the value after adding, so it is
           // easy for the user to add more! 
       }
    }
}
</script>
   
<style>

</style>