<template>
  <div ref="mark">
    <slot></slot>
  </div>
</template>

<script>
import Mark from 'mark.js';

export default {
  name: 'mark-js',

  props: {
    mark: String
  },

  mounted() {
    this.instance = new Mark(this.$refs.mark);
    this.instance.mark(this.mark);
  },

  watch: {
    mark(value) {
      this.instance.unmark();
      this.instance.mark(value);
    }
  }
}
</script>

<style>
</style>
