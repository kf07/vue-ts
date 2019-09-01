<template>
    
</template>

<script lang="ts">
    import Vue from "vue"
  export default Vue.extend({
    name: "Form",
    data:() => ({
      defaultDateLavel: "1980-01-01",
      dateLabel: null as string | null
    }),
    computed: {
      dateFormLabel(): Date {
        let label = this.defaultDateLavel
        if (this.dateLabel !== null) {
          label = this.dateLabel
        }
        return new Date(label)
      }
    }
  })
</script>

<style scoped>

</style>