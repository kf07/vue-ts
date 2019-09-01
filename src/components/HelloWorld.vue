<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script lang="ts">
import Vue, { PropType } from 'vue';

export default Vue.extend({
  name: 'HelloWorld',
  props: {
    obj: {
      type: Object as PropType<{ name: string }>,
      required: true
    },
    arr: {
      type: Array as PropType<{ task: string}[]>
    }
  },
  computed: {
    myName(): string {
      return this.obj.name
    },
    myFirstTask(): string {
      return this.arr[0].task
    }
  }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
