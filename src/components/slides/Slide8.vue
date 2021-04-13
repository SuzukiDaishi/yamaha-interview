<template>
  <BaseSlideCenter class="slide8__bg-color">
    <div class="slide8__title">
        面白い技術で<br>
        革新的な体験を
    </div>
  </BaseSlideCenter>
</template>

<script>
import BaseSlideCenter from '../BaseSlideCenter.vue'
import gsap from 'gsap'

export default {
  name: 'Slide8',
  components: {
    BaseSlideCenter,
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
      this.addEventScroll('slide8', (rect) => {
        let left =  this.$el.getBoundingClientRect().left - rect.left
        let earlyStartPixcel = window.innerWidth
        console.log(left - earlyStartPixcel);
        if ( left - earlyStartPixcel < 0 ) {
            gsap.from('.slide8__title', {duration: 2.5, ease: 'Power1.easeOut', opacity: 0, scale: 0  })
            this.removeEventScroll('slide8')
        }
      })
    }
  },
}
</script>

<style scoped>
.slide8__title {
  font-size: 6vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: aliceblue;
  text-shadow: 2px 0px 5px rgba(0,0,0,0.3);
  background: rgba(0,0,0,0.3);
  width: 70vw;
  height: 70vh;
  box-shadow: rgba(14, 30, 37, 0.12) 0px 4px 8px 0px, rgba(14, 30, 37, 0.32) 0px 4px 32px 0px;
  border-radius: 10px;
}
.slide8__bg-color {
  background-image: linear-gradient(to top, #fcc5e4 0%, #fda34b 15%, #ff7882 35%, #c8699e 52%, #7046aa 71%, #0c1db8 87%, #020f75 100%);
}
</style>