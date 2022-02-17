<template>
  <div class="todo-list">
      <h2 v-show="todos.length == 0">This list is empty</h2>
      <ul v-for="todo in todos" :key="todo">
          <li :class="{done : todo.done}"> <input type="checkbox" name="done" v-model="todo.done" id=""> {{todo.content}} <button @click="getTodo(todo)">X</button></li>
      </ul>
  </div>
</template>

<script>
export default {
    props: ['todos'],
    methods: {
        getTodo(todo){
            const index = this.todos.indexOf(todo)
            this.todos.splice(index, 1)
        }
    }
}
</script>

<style>
    .done{
        text-decoration: line-through;
    }
</style>