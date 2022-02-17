<template>
  <div class="todo">
    <!-- Todo Header -->
    <TodoHeader :todosNumber="todoNumber"/>
    <!-- Todo Input -->
    <TodoInput @add-todo="addTodo" />
    <!-- Todo List -->
    <TodoList :todos="todos"/>
  </div>
</template>

<script>
import TodoHeader from './TodoHeader.vue'
import TodoList from './TodoList.vue'
import TodoInput from './TodoInput.vue'

let id = 0
export default {
  components: {
    TodoHeader,
    TodoList,
    TodoInput
},
    data(){
      return {
        todosNumber: 0,
        todos : [
          {id : id++, content: 'This is a sample content', done: false},
          {id : id++, content: 'Make a checkout app in vuejs', done: false},
          {id : id++, content: 'Recording first youtube video', done: false}
        ]
      }
    },
    methods:{
      addTodo(content){
        this.todos.push({id: id++, content: content, done: false})
      }
    },
    computed: {
      todoNumber(){
        return this.todos.length
      }
    }
}
</script>

<style>

</style>