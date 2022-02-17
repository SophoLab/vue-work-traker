<template>
  <div class="todo-input">
      <input type="text" v-model="text">
      <button @click="addTodo">Test</button>
  </div>
</template>

<script>
export default {
    data(){
        return {
            text: ''
        }
    },
    methods: {
        addTodo(){
            this.$emit('addTodo', this.text)
            this.text = ''
        }
    }
    
}
</script>

<style>

</style>