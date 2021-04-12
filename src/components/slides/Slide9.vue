<template>
  <BaseSlideCenter class="slide8__bg-color">
    <div class="slide9__title">
        ご静聴ありがとうございました
    </div>
  </BaseSlideCenter>
</template>

<script>
import BaseSlideCenter from '../BaseSlideCenter.vue'
export default {
  name: 'Slide8',
  components: {
    BaseSlideCenter,
  },
}
</script>

<style scoped>
.slide9__title {
  font-size: 3.5vw;
  text-shadow: 1px 0px 5px rgba(0,0,0,0.3);
}
.slide9__bg-color {
  background-image: linear-gradient(to top, #f3e7e9 0%, #e3eeff 99%, #e3eeff 100%);
}
</style>