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
export default {
  name: 'Slide8',
  components: {
    BaseSlideCenter,
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