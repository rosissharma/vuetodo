<template>
  <div class="container">
      <div v-for="todo in todos" v-bind:key="todo.id">
        <ul class="list-group" v-bind:class="{ completed: todo.completed }">
          <li class="list-group-item">
            <input type="checkbox" v-bind:checked="todo.completed" @change="completed" />
            {{ todo.task }}
            <button @click="$emit('delete-todo', todo.id)" class="btn btn-danger">X</button>
          </li>
        </ul>
      </div>
    </div>
</template>

<script>

export default {
  name: "Todos",
  props: ["todos"],
  methods: {
      completed() {
          this.todo.completed = !this.todo.completed
      }
  }
};
</script>

<style>
.list-group-item {
  margin: 5px;
}

.completed {
  text-decoration: line-through;
  color: #aaa;
}

.btn {
  float: right;
}
</style>