<template>
  <div id="app">
    <h1 class="text-center">Todo</h1>
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:delete-todo="deleteTodo" />
  </div>
</template>

<script>
import AddTodo from './components/AddTodo.vue'
import Todos from './components/Todos.vue'

export default {
  name: 'App',
  components: {
    AddTodo, Todos
  },
  data() {
    return {
      todos: [
        {id:1, task: 'walk the dog', completed:true},
        {id:2, task: 'cook', completed:false},
        {id:3, task: 'clean', completed:false}
      ]
    }
  },
  methods: {
    addTodo(todo) {
      //add it to the array
      //... is used to expand the array
      this.todos = [...this.todos, todo]
    },
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
