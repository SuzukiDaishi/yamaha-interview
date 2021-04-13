<template>
  <BaseSlideCenter class="slide8__bg-color">
    <div class="slide9__title">
        <span class="slide9__c1">本</span>
        <span class="slide9__c2">日</span>
        <span class="slide9__c3">は</span>
        <span class="slide9__c4">よ</span>
        <span class="slide9__c5">ろ</span>
        <span class="slide9__c6">し</span>
        <span class="slide9__c7">く</span>
        <span class="slide9__c8">お</span>
        <span class="slide9__c9">ね</span>
        <span class="slide9__c10">が</span>
        <span class="slide9__c11">い</span>
        <span class="slide9__c12">し</span>
        <span class="slide9__c13">ま</span>
        <span class="slide9__c14">す</span>
    </div>
  </BaseSlideCenter>
</template>

<script>
import BaseSlideCenter from '../BaseSlideCenter.vue'
import gsap from 'gsap'

export default {
  name: 'Slide9',
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
      this.addEventScroll('slide9', (rect) => {
        let left =  this.$el.getBoundingClientRect().left - rect.left
        let earlyStartPixcel = window.innerWidth
        console.log(left - earlyStartPixcel);
        if ( left - earlyStartPixcel < 0 ) {
          let tl = gsap.timeline()
          for (let i=1; i<=14; i++) {
            tl.from(`.slide9__c${i}`, {duration: .25, opacity: 0, })
          }
          this.removeEventScroll('slide9')
        }
      })
    }
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