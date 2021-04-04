<template>
  <BaseSlidePage>
    <div class="center-outer">
      <div class="center-inner">
        <h1 class="title">YAMAHA最終面接<br />自己PR</h1>
      </div>
    </div>
  </BaseSlidePage>
</template>

<script>
import BaseSlidePage from '../BaseSlidePage.vue'

export default {
  name: 'Slide2',
  components: {
    BaseSlidePage
  },
  props: {
    addEventScroll: {
      type: Function,
      default: null,
    }
  },
  mounted() {
    if (this.addEventScroll!==null) {
      this.addEventScroll((rect) => {
        let left =  this.$el.getBoundingClientRect().left - rect.left
        if ( left <= 0 ) {
          console.log('animation');
        }
      })
    }
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
  top: 50%;
  left: 50%;
  transform: translateY(-50%) translateX(-50%);
}
.title {
  font-size: 8vh;
}
</style>