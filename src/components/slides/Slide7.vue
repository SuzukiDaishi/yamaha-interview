<template>
  <BaseSlideCenter class="slide7__bg-color">
    <h2 class="slide7__title">目標</h2>
  </BaseSlideCenter>
</template>

<script>
import BaseSlideCenter from '../BaseSlideCenter.vue'
export default {
  name: 'Slide7',
  components: {
    BaseSlideCenter
  },
}
</script>

<style scoped>
.slide7__title {
  font-size: 6vw;
  color: aliceblue;
  text-shadow: 1px 0px 5px rgba(0,0,0,0.3);
}
.slide7__bg-color {
  background-image: linear-gradient(-45deg, #FFC796 0%, #FF6B95 100%);
}
</style>