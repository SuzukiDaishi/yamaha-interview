<template>
    <BaseSlidePage class="slide6__content">
        <div class="slide6__title-wrapper">
            <h2 class="slide6__title">Skils</h2>
        </div>
        <div class="slide6__list">
            <ul>
                <li>ウェブ</li>
                <ul>
                    <li>フロントエンド</li>
                    <li>バックエンド</li>
                </ul>
                <li>モバイル</li>
                <ul>
                    <li>iOS</li>
                    <li>Android</li>
                </ul>
                <li>深層学習</li>
                <ul>
                    <li>生成モデル</li>
                    <li>音声</li>
                </ul>
                <li>
                    etc...
                </li>
            </ul>
        </div>
        <img src='./images/アイコン.png' class="slide6__img" >
    </BaseSlidePage>
</template>

<script>
import BaseSlidePage from '../BaseSlidePage.vue'

export default {
  name: 'Slide6',
  components: {
    BaseSlidePage,
  },
}
</script>

<style scoped>
.slide6__content {
    background-image: linear-gradient(to right, #92fe9d 0%, #00c9ff 100%);
}
.slide6__title {
    font-size: 4vw;
    padding: 20px 0;
    margin: 0;
    text-shadow: 1px 0px 5px rgba(0,0,0,0.3);
}
.slide6__title-wrapper {
    margin: 0 2vw;
    border-bottom: solid 3px black;
}
.slide6__list {
    margin: 0 2vw;
    font-size: 3em;
    line-height: 80px;
    height: 75vh;
    text-shadow: 1px 0px 5px rgba(0,0,0,0.3);
}
.slide6__img {
    position: relative;
    top: -75vh;
    left: 400px;
    height: 75vh;
    filter: drop-shadow(2px 2px 2px rgba(160, 160, 160, 0.8));
}
</style>