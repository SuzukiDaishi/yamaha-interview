<template>
  <BaseSlidePage class="bg-color">
    <div class="center-outer">
      <div class="center-inner">
        <h1 class="title">YAMAHA最終面接<br />〜 自己PR 〜</h1>
      </div>
    </div>
  </BaseSlidePage>
</template>

<script>
import BaseSlidePage from '../BaseSlidePage.vue'

export default {
  name: 'Slide1',
  components: {
    BaseSlidePage
  },
  mounted() {
  },
}
</script>

<style scoped>
.center-outer {
  position: relative;
  width: 100vw;
  height: 100vh;
}
.center-inner {
  position: absolute;
  text-align: center;
  top: 50%;
  left: 50%;
  transform: translateY(-50%) translateX(-50%);
}
.title {
  font-size: 8vh;
  color: aliceblue;
  text-shadow: 1px 0px 5px rgba(0,0,0,0.3);
}
.bg-color {
  background: linear-gradient(135deg, #427eff 0%, #f13f79 70%) no-repeat;
}
</style>