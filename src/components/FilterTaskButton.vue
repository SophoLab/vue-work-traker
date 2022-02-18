<template>
    <button @click="taskFilter">{{showTask}}</button>
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