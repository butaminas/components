<template>
  <div class="ball-grid-beat vue-loaders" :style="rootStyles">
    <div :style="styles"></div>
    <div :style="styles"></div>
    <div :style="styles"></div>
    <div :style="styles"></div>
    <div :style="styles"></div>
    <div :style="styles"></div>
    <div :style="styles"></div>
    <div :style="styles"></div>
    <div :style="styles"></div>
  </div>
</template>

<script>
export default {
  name: 'BallGridBeatLoader',
  props: {
    size: String,
    color: String
  },
  computed: {
    rootStyles() {
      return {
        width: `calc(3 * (${this.size || '15px'} + 4px))`
      };
    },
    styles() {
      const size = this.size ? String(this.size) : null;
      const color = this.color ? String(this.color) : null;

      if (!color && !size) {
        return;
      }

      const styles = {};

      if (size) {
        styles.width = styles.height = size;
      }

      if (color) {
        styles.backgroundColor = color;
      }

      return styles;
    }
  }
};
</script>

<style>
</style>
