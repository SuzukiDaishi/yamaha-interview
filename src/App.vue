<template>
  <div id="slide-app">
    <vue-scroll-snap id="scrollWrapper" :fullscreen="true" :horizontal="true">
      <Slide1 class="item" />
      <Slide2 class="item" :addEventScroll="addEventScroll" :removeEventScroll="removeEventScroll"/>
      <Slide3 class="item" />
      <Slide4 class="item"/>
      <Slide5 class="item"/>
      <Slide6 class="item"/>
      <Slide7 class="item"/>
      <Slide8 class="item"/>
      <Slide9 class="item"/>
    </vue-scroll-snap>
  </div>
</template>

<script>
import VueScrollSnap from 'vue-scroll-snap'
import Slide1 from './components/slides/Slide1'
import Slide2 from './components/slides/Slide2'
import Slide3 from './components/slides/Slide3'
import Slide4 from './components/slides/Slide4'
import Slide5 from './components/slides/Slide5'
import Slide6 from './components/slides/Slide6'
import Slide7 from './components/slides/Slide7'
import Slide8 from './components/slides/Slide8'
import Slide9 from './components/slides/Slide9'

export default {
  name: 'App',
  components: {
    VueScrollSnap,
    Slide1,
    Slide2,
    Slide3,
    Slide4,
    Slide5,
    Slide6,
    Slide7,
    Slide8,
    Slide9,
  },
  data() {
    return {
      eventList: {}, // スクロール時に実行される関数の一覧
    };
  },
  mounted() {
    // スクロール時に実行
    this.$el.querySelector('#scrollWrapper').addEventListener('scroll', (e) => {
      this.doEventScroll(e.target.getBoundingClientRect());
    });
  },
  methods: {
    /** スクロール時に追加する動作の追加 */
    addEventScroll(key, action) {
      this.eventList[key] = action;
    },
    /** スクロール時に追加する動作の削除 */
    removeEventScroll(key) {
      delete this.eventList[key];
    },
    /** スクロール時に登録された動作を実行 */
    doEventScroll(rect) {
      for (let k in this.eventList) {
        this.eventList[k](rect);
      }
    },
  },
};
</script>

<style>
#slide-app {
  font-family: "Helvetica Neue", Arial, "Hiragino Kaku Gothic ProN", "Hiragino Sans",
    "BIZ UDPGothic", Meiryo, sans-serif;
  font-feature-settings: "palt";
}
</style>
