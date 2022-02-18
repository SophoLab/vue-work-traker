<template>
  <div class="todo">
    <!-- Todo Header -->
    <TodoHeader :todosNumber="todoNumber"/>
    <!-- Todo Input -->
    <TodoInput @add-todo="addTodo" />
    <!-- Todo List -->
    <TodoList :todos="filterTask"/>
    <!-- Todo Filter Button -->
    <FilterTaskButton @task-filter="taskFilter" />

  </div>
</template>

<script>
import TodoHeader from './TodoHeader.vue'
import TodoList from './TodoList.vue'
import TodoInput from './TodoInput.vue'
import FilterTaskButton from './FilterTaskButton.vue'

let id = 0
export default {
  components: {
    TodoHeader,
    TodoList,
    TodoInput,
    FilterTaskButton
},
    data(){
      return {
        todosNumber: 0,
        showTask: null,
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
      },
      taskFilter(displayTask){
        this.showTask = displayTask
    }
    },
    computed : {
      todoNumber(){
        return this.taskNotDone.length
      },
      filterTask(){
          return this.showTask ? this.taskDone : this.todos
        },
      taskDone(){
          return this.todos.filter((task) => {return task.done == true})
        },
      taskNotDone(){
          return this.todos.filter((task) => {return task.done == false})
      }
    }
}
</script>

<style>

</style>