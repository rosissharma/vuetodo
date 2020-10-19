<template>
  <div class="container">
        <form @submit="addTodo">
            <div class="form-group">
                <input type="text" v-model="task" placeholder="enter your task" required class="form-control" />
                <br>
                <button class="btn btn-dark btn-block">Add Task</button>
                <br><br>
            </div>
        </form>
  </div>
</template>

<script>
export default {
    name: 'AddTodo',
    data() {
        return {
            task: ''
        }
    },
    methods: {
        addTodo(e) {
            e.preventDefault()

            const newTodo = {
                id:Date.now(), 
                task: this.task, 
                completed: false
            }

            //send data to parent
            this.$emit('add-todo', newTodo)

            //clear out the input field
            this.task = ''
        }
    }
}
</script>

<style>

</style>