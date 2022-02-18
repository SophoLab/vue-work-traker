<template>
  <div class="todo-list mt-5">
    <div v-show="todos.length == 0" class="mb-4">This list is empty...⚠️ </div>
      <ul>
          <li v-for="todo in todos" :key="todo"  :class="{done : todo.done, 'font-bold' : todo.done}" class="mb-2"> 
              <input type="checkbox" name="done" v-model="todo.done" id=""> {{todo.content}} 
              <button @click="getTodo(todo)">❌</button>
        </li>
      </ul>
  </div>
</template>

<script>
export default {
    props: ['todos'],
    data(){
        return {
           
        }
    },
    methods: {
        getTodo(todo){
            const index = this.todos.indexOf(todo)
            this.todos.splice(index, 1)
        },
       
    }
}
</script>

<style>
    .done{
        text-decoration: line-through;
    }
</style>