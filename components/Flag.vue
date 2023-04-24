<template>
  <div class="rabtle-container" :style="{left: left + 'px'}">
    <emojione-monotone-flag-for-chequered-flag />
  </div>
</template>

<script>
export default {
  props: {
    left: Number,
  },
}
</script>
