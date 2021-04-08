<template>
    <BaseSlidePage>
        <div class="center-outer">
            <div class="center-inner">
                <slot />
            </div>
        </div>
    </BaseSlidePage>
</template>

<script>
import BaseSlidePage from './BaseSlidePage.vue'

export default {
    name: 'BaseSlideTitleOnly',
    components: {
        BaseSlidePage,
    },
}
</script>

<style>
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
</style>