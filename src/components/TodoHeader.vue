<template>
  <div class="todo-header">
      <span>You've got {{ todosNumber }} coming up in the next days</span>
  </div>
</template>

<script>
export default {
    props: ['todosNumber']
}
</script>

<style>

</style>