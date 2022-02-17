<script>
      export default {
        data() {
          return {
            msg : 'Hello From Vuejs Planet',
            count : 0
          }
        },
        methods : {
          subOne(){
            this.count > 0 ? this.count-- : null
          }
        }
      }
</script>

<template>
  <div class="main">
    {{ msg }}
    <h3>Count {{count}}</h3>
    <button @click="count++">Add 1</button>
    <button @click="subOne">Sub 1</button>
    <button @click="count = 0">Reset</button>
  </div>
</template>

<style scoped>

</style>
