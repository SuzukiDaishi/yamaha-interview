<template>
    <BaseSlidePage>
        <div class="slide4__container">
            <div v-for="i in 15" :key="i">{{i}}</div>
        </div>
    </BaseSlidePage>
</template>

<script>
import BaseSlidePage from '../BaseSlidePage.vue'

export default {
  name: 'Slide4',
  components: {
    BaseSlidePage
  },
  mounted() {
  },
}
</script>

<style scoped>
.slide4__container {
    width: 100vw;
    height: 100vh;
    display: flex;
    flex-wrap: wrap;
}
.slide4__container > div {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    width: 20%;
    background: linear-gradient(135deg, #427eff 0%, #f13f79 70%) no-repeat;
    height: calc(100%/3);
}
</style>