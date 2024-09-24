<template>
  <div class="rabbit-container" :style="{left: pos + 'px'}">
    <emojione-monotone-rabbit class="icon" />
    <div
      class="py-1 px-1 text-xs bg-white bg-opacity-20 rounded-md text-center"
      :class="[isLatter ? 'float-left' : 'float-right']"
      :style="{
        width: tooltipWidth + 'px',
        display: showSlideNum ? 'block' : 'none'
      }"
    >
      {{props.current}} / {{total}}
    </div>
  </div>
</template>

<script setup>
import { computed } from 'vue';

const showSlideNum = $slidev.configs?.rabbit?.slideNum ?? false;

const total = $slidev.nav.total;
const canvasWidth = $slidev.configs.canvasWidth;
const tooltipWidth = showSlideNum ? 60 : 0;
const marginRight = 20; // To display rabbit icon on last page

const props = defineProps({
  current: Number,
});

const isLatter = computed(() => props.current > (total / 2));

const pos = computed(() => {
  if (props.current === 1 || total === 1) {
    return 0;
  }
  // Calculate the width of slide
  const width = canvasWidth - marginRight - (isLatter.value ? tooltipWidth : 0);
  return (props.current - 1 ) * (width / (total - 1));
});

</script>

