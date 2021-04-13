<template>
  <BaseSlideCenter class="slide7__bg-color">
    <h2 class="slide7__title">目標</h2>
  </BaseSlideCenter>
</template>

<script>
import BaseSlideCenter from '../BaseSlideCenter.vue'
import gsap from 'gsap'

export default {
  name: 'Slide7',
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
      this.addEventScroll('slide7', (rect) => {
        let left =  this.$el.getBoundingClientRect().left - rect.left
        let earlyStartPixcel = window.innerWidth
        console.log(left - earlyStartPixcel);
        if ( left - earlyStartPixcel < 0 ) {
            gsap.from('.slide7__title', {duration: 2.5, ease: 'Power1.easeOut', opacity: 0 })
            this.removeEventScroll('slide7')
        }
      })
    }
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