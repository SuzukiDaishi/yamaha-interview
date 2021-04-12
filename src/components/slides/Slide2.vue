<template>
  <BaseSlide2Split id='slide2' rightImageUrl="/yamaha-interview/images/IMG_0376.JPG">
    <div class="slide2__container">
      <div class="slide2__contentbox slide2__fadein1">
        <h2 class="slide2__h2 slide2__nomp">
          <ruby>
            鈴木<rt>スズキ</rt>
            大志<rt>ダイシ</rt>
          </ruby>
        </h2>
        <b class="slide2__text">金沢工業大学 工学部 情報工学科 4年</b>
      </div>
      <div class="slide2__contentbox slide2__fadein2">
        <h3 class="slide2__h3 slide2__nomp">年齢</h3>
        <ul>
          <li class="slide2__text">21歳</li>
        </ul>
      </div>
      <div class="slide2__contentbox slide2__fadein3">
        <h3 class="slide2__h3 slide2__nomp">住んでるところ</h3>
        <ul>
          <li class="slide2__text">石川県金沢市</li>
        </ul>
      </div>
      <div class="slide2__contentbox slide2__fadein4">
        <h3 class="slide2__h3 slide2__nomp">趣味</h3>
        <ul>
          <li class="slide2__text">音楽 🎶</li>
          <li class="slide2__text">お散歩 🚶‍♂️</li>
          <li class="slide2__text">温泉巡り ♨️</li>
        </ul>
      </div>
    </div>
  </BaseSlide2Split>
</template>

<script>
import BaseSlide2Split from '../BaseSlide2Split.vue'
import gsap from 'gsap'

export default {
  name: 'Slide2',
  components: {
    BaseSlide2Split
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
      this.addEventScroll('slide2', (rect) => {
        let left =  this.$el.getBoundingClientRect().left - rect.left
        let earlyStartPixcel = window.innerWidth
        if ( left - earlyStartPixcel <= 0 ) {
          let tl = gsap.timeline()
          tl.from('.slide2__fadein1', {duration: 1, opacity: 0 })
          tl.from('.slide2__fadein2', {duration: 0.5, opacity: 0 })
          tl.from('.slide2__fadein3', {duration: 0.5, opacity: 0 })
          tl.from('.slide2__fadein4', {duration: 0.5, opacity: 0 })
          this.removeEventScroll('slide2')
        }
      })
    }
  },
}
</script>

<style scoped>
#slide2 {
  background-image: linear-gradient(-20deg, #e9defa 0%, #fbfcdb 100%);
}
.slide2__container {
  margin: 5% 5%;
}
.slide2__nomp {
  padding: 0;
  margin: 0;
}
.slide2__h2 {
  font-size: 5vw;
}
.slide2__contentbox {
  padding: 5%;
  padding-top: 10px;
  padding-bottom: 10px;
  margin-top: 10px;
  border-radius: 10px;
  text-shadow: 1px 0px 5px rgba(0,0,0,0.3);
  box-shadow: rgba(14, 30, 37, 0.12) 0px 2px 4px 0px, rgba(14, 30, 37, 0.32) 0px 2px 16px 0px;
  background-image: linear-gradient(120deg, #fdfbfb 0%, #ebedee 100%);
}
.slide2__h3 {
  font-size: 1.7vw;
}
.slide2__text {
  font-size: 1.5vw;
}
</style>