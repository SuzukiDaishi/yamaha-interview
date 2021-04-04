<template>
  <div id="slide-app">
    <vue-scroll-snap id="scrollWrapper" :fullscreen="true" :horizontal="true">
      <Slide1 class="item" />
      <Slide2 class="item" :addEventScroll="addEventScroll" />
      <Slide2 class="item" />
      <Slide2 class="item" />
    </vue-scroll-snap> 
  </div>
</template>

<script>
import VueScrollSnap from 'vue-scroll-snap'
import Slide1 from './components/slides/Slide1'
import Slide2 from './components/slides/Slide2'

export default {
  name: 'App',
  components: {
    VueScrollSnap,
    Slide1,
    Slide2
  },
  data() {
    return {
      eventList: [] // スクロール時に実行される関数の一覧
    }
  },
  mounted() {
    // スクロール時に実行
    this.$el.querySelector('#scrollWrapper').addEventListener('scroll', (e) => {
      this.doEventScroll(e.target.getBoundingClientRect())
    })
  },
  methods: {
    /** スクロール時に追加する動作の追加 */
    addEventScroll(action) {
      this.eventList.push(action)
    },
    /** スクロール時に登録された動作を実行 */
    doEventScroll(rect) {
      for (let i in this.eventList) {
        this.eventList[i](rect)
      }
    }
  }
}
</script>

<style>
#slide-app {
  font-family: "Helvetica Neue",
    Arial,
    "Hiragino Kaku Gothic ProN",
    "Hiragino Sans",
    "BIZ UDPGothic",
    Meiryo,
    sans-serif;
}
</style>