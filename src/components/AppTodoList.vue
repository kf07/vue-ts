<template>
    <div class="todos">
        <div v-for="todo in todos" :key="todo.id">
            <AppTodoItem :todo="todo" />
        </div>
    </div>
</template>

<script lang="ts">
  import Vue from "vue"
  import AppTodoItem,{ Todo } from "@/components/AppTodoItem.vue";

  export type Data = {
    todos: Todo[]
  }
  export default Vue.extend({
    name: "AppTodoList",
    data: (): Data => ({
      todos:[
        {
          id: 1,
          task: 'test',
          done: false
        }
      ]
    }),
    components: {
      AppTodoItem
    }
  })
</script>

<style scoped>

</style>