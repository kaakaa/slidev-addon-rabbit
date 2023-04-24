<template>
  <div class="rabtle-container" :style="{left: pos + 'px'}">
    <emojione-monotone-rabbit class="icon" />
  </div>
</template>

<script>
export default {
  props: {
    current: Number
  },
  data() {
    return {
      left: this.current,
    }
  },
  computed: {
    pos: function() {
      const total = this.$slidev.nav.total;
      const maxWidth = this.$slidev.configs.canvasWidth - 20;
      return (this.current - 2 )    // "current - 2" because icon is placed at the start position when opening the second page
        * (maxWidth / (total - 2)); // "total - 2" because first and last page isn't counted
    }
  }
};
</script>
