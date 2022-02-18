<template>
  <div class="todo-input">
      <input type="text" v-model="text" @keyup.enter="addTodo" class="border-2 rounded border-gray-400 outline-none w-1/3 h-10"/>
      <button @click="addTodo" class="border border-solid py-2 px-5 ml-2 border-yellow-400 bg-amber-500 hover:bg-amber-600 text-white font-bold">Test</button>
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