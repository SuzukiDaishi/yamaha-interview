<template>
  <BaseSlideCenter class="slide1__bg-color">
    <h1 class="slide1__title">YAMAHA最終面接<br />〜 自己PR 〜</h1>
  </BaseSlideCenter>
</template>

<script>
import BaseSlideCenter from '../BaseSlideCenter.vue'
import gsap from 'gsap'

export default {
  name: 'Slide1',
  components: {
    BaseSlideCenter
  },
  mounted() {
    gsap.from('.slide1__title', {duration: 2.5, ease: 'bounce.out', opacity: 0, y: -300})
  },
}
</script>

<style scoped>
.slide1__title {
  font-size: 6vw;
  color: aliceblue;
  text-shadow: 1px 0px 5px rgba(0,0,0,0.3);
}
.slide1__bg-color {
  background: linear-gradient(135deg, #427eff 0%, #f13f79 70%) no-repeat;
}
</style>