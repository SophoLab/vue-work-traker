<template>
  <div class="todo-list">
      <h2 v-show="todos.length == 0">This list is empty</h2>
      <ul v-for="todo in todos" :key="todo">
          <li>{{todo.content}}</li>
      </ul>
  </div>
</template>

<script>
export default {
    props: ['todos']
}
</script>

<style>

</style>