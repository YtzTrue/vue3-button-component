<script setup>
import icons from '@/icons.js';

const props = defineProps({
  name: {
    type: String
  },
  fill: {
    type: String,
    default: 'white'
  },
  size: {
    type: String,
    default: 'normal'
  }
})

</script>

<template>
  <svg :width="size === 'small' ? 24 : 30" :height="size === 'small' ? 24 : 30" viewBox="0 0 30 30" :fill="fill"
    xmlns="http://www.w3.org/2000/svg" v-html="icons[this.name]">
  </svg>
</template>

<style scoped lang="scss">
svg {
  vertical-align: bottom;

  @media(max-width: 640px) {
    width: 24px;
    height: 24px;
  }
}
</style>
