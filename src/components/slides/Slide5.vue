<template>
    <BaseSlidePage class="slide5__content">
        <div class="slide5__title-wrapper">
            <h2 class="slide5__title">深層生成モデルによる声質変換</h2>
        </div>
        <div class="slide5__img-wrapper">
            <img src="/yamaha-interview/images/vc.png" class="slide5__img" />
            <div>
                <audio class="slide5__audio" src="/yamaha-interview/waves/sound_1.wav" controls />
                <audio class="slide5__audio" src="/yamaha-interview/waves/sound_2.wav" controls />
                <audio class="slide5__audio" src="/yamaha-interview/waves/sound_3.wav" controls />
            </div>
        </div>
    </BaseSlidePage>
</template>

<script>
import BaseSlidePage from '../BaseSlidePage.vue'
import gsap from 'gsap'

export default {
  name: 'Slide5',
  components: {
    BaseSlidePage,
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
      this.addEventScroll('slide5', (rect) => {
        let left =  this.$el.getBoundingClientRect().left - rect.left
        let earlyStartPixcel = window.innerWidth
        console.log(left - earlyStartPixcel);
        if ( left - earlyStartPixcel < 0 ) {
            gsap.from('.slide5__img', {duration: 2, ease: 'Linear.easeNone', opacity: 0, scale: 0 })
            this.removeEventScroll('slide5')
        }
      })
    }
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
.slide5__audio {
    margin: 0 20px;
}
</style>