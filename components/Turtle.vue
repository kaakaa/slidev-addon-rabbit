<template>
  <div class="rabtle-container" :style="{left: left + 'px'}">
    <emojione-monotone-turtle class="icon" />
  </div>
</template>

<script>
export default {
  props: {
    current: Number
  },
  data() {
    const maxWidth = this.$slidev.configs.canvasWidth - 20; // 20 is margin-right
    const time = this.$route?.query?.time || 10;
    return {
      left: 0,
      intervalId: null,
      maxWidth: maxWidth,
      speed: maxWidth / (time * 60 * 10) // 100ms毎の変化量
    }
  },
  beforeUpdate() {
    // Reset when opening the first page
    if (this.current == 1) {
      this.left = 0;
      if (this.intervalId) {
        clearInterval(this.intervalId);
        this.intervalId = null;
      }
    }
    // do nothing if the turtle already starts
    if (this.intervalId) {
      return;
    }
    // let the turtle run
    this.intervalId = setInterval(() => {
      if (this.left < this.maxWidth) {
        this.left += this.speed;
      }
    }, 100); // update per 100ms
  }
};
</script>
