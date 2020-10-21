<template>
  <div class="container">
      <div v-for="todo in todos" v-bind:key="todo.id">
        <ul class="list-group"">
          <li class="list-group-item">
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
};
</script>

<style>
.list-group-item {
  margin: 5px;
}

.btn {
  float: right;
}
</style>
