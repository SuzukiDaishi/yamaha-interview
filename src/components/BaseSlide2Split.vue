<template>
  <BaseSlidePage>
    <div class="sp2__content">
      <div class="sp2__photo" :style="{'background-image': `url(${rightImageUrl})`}">
      </div>
      <div class="sp2__text">
          <slot />
      </div>
    </div>
  </BaseSlidePage>
</template>

<script>
import BaseSlidePage from './BaseSlidePage.vue'


export default {
  name: 'BaseSlide2Split',
  components: {
    BaseSlidePage
  },
  props: {
    rightImageUrl: {
        type: String,
        default: '',
    }
  },
}
</script>

<style>
.sp2__content {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  flex-grow: 1;
  width: 100%;
  height: 100%;
}
.sp2__photo {
  width: 50%;
  background-image: url('/images/IMG_0376.JPG');
  background-size: cover;
}
.sp2__text {
  width: 50%;
}
</style>