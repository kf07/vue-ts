<template>
    <div class="hello">
        <div @click="onClickElement">
            ボタン
        </div>
    </div>
</template>

<script lang="ts">
  import Vue, {PropType} from 'vue';

  export type Rect = {
    width: number
    height: number
  }
  export type Position = {
    top: number
    left: number
  }
  export default Vue.extend({
    name: 'HelloWorld',
    data: () => ({
      bounds: null as ClientRect | DOMRect | null
    }),
    methods: {
      onClickElement(event: Event): void {
        if (!event.isTrusted) return
        if (event.target instanceof HTMLElement) {
          this.bounds = event.target.getBoundingClientRect()
        }
      }
    },
    computed: {
      boundInfo(): string {
        if (this.bounds === null) return ""
        return JSON.stringify(this.bounds)
      },
      rect(): Rect {
        if (this.bounds === null) return {width: 0, height: 0}
        return {
          width: this.bounds.width,
          height: this.bounds.height
        }
      },
      position(): Position {
        if (this.bounds === null) return {top: 0, left: 0}
        return {
          top: this.bounds.top,
          left: this.bounds.left
        }
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
