<template>
    <BaseSlidePage class="slide5__content">
        <div class="slide5__title-wrapper">
            <h2 class="slide5__title">深層変換モデルによる性質変換</h2>
        </div>
        <div class="slide5__img-wrapper">
            <img src="/images/vc.png" class="slide5__img" />
        </div>
    </BaseSlidePage>
</template>

<script>
import BaseSlidePage from '../BaseSlidePage.vue'

export default {
  name: 'Slide5',
  components: {
    BaseSlidePage,
  },
}
</script>

<style scoped>
.slide5__content {
    background-image: linear-gradient(45deg, #93a5cf 0%, #e4efe9 100%);
}
.slide5__title {
    font-size: 3.2vw;
    padding: 20px 0;
    margin: 0;
    text-shadow: 1px 0px 5px rgba(0,0,0,0.3);
}
.slide5__title-wrapper {
    margin: 0 2vw;
    border-bottom: solid 3px black;
}
.slide5__img-wrapper {
    width: 100%;
    padding-top: 15vh;
    text-align: center;
}
.slide5__img {
    width: 80vw;
}
</style>