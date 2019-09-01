<template>

</template>

<script lang="ts">
    import Vue from "vue"
  export default Vue.extend({
    name: "AppTodoList",
    data: () => ({
      firstName: '',
      lastName: '',
      doneTodos: null as null | boolean,
      todos: [] as Array<{
        id: string
        task: string
        done: boolean
      }>
    })
  })
</script>

<style scoped>

</style>