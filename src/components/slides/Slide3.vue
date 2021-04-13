<template>
  <BaseSlideCenter class="slide3__bg-color">
    <h2 class="slide3__title">Works</h2>
  </BaseSlideCenter>
</template>

<script>
import BaseSlideCenter from '../BaseSlideCenter.vue'
import gsap from 'gsap'

export default {
  name: 'Slide3',
  components: {
    BaseSlideCenter
  },
  props: {
    addEventScroll: {
      type: Function,
      default: null,
    },
    removeEventScroll: {
      type: Function,
      default: null,
    }
  },
  mounted() {
    if (this.addEventScroll!==null && this.removeEventScroll!==null) {
      this.addEventScroll('slide3', (rect) => {
        let left =  this.$el.getBoundingClientRect().left - rect.left
        let earlyStartPixcel = window.innerWidth
        console.log(left - earlyStartPixcel);
        if ( left - earlyStartPixcel < 0 ) {
          gsap.from('.slide3__title', {duration: 2, ease: 'Power1.easeInOut', opacity: 0, x: 300})
          this.removeEventScroll('slide3')
        }
      })
    }
  },
}
</script>

<style scoped>
.slide3__title {
  font-size: 6vw;
  color: aliceblue;
  text-shadow: 1px 0px 5px rgba(0,0,0,0.3);
}
.slide3__bg-color {
  background-image: linear-gradient(to top, #3f51b1 0%, #5a55ae 13%, #7b5fac 25%, #8f6aae 38%, #a86aa4 50%, #cc6b8e 62%, #f18271 75%, #f3a469 87%, #f7c978 100%);
}
</style>