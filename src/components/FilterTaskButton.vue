<template>
    <button @click="taskFilter" class="border border-solid py-2 px-5  border-yellow-400 bg-amber-500 hover:bg-amber-600 text-white font-bold" >{{showTask}}</button>
</template>

<script>
export default {
    data(){
        return {
            displayTask: false
        }
    },
    methods: {
        taskFilter(){
            this.displayTask = !this.displayTask
            this.$emit('taskFilter', this.displayTask)
        }
    },
    computed: {
        showTask(){
            return this.displayTask ? 'Show All Task' : 'Show Complete Task'
        }
    }
}
</script>

<style>

</style>