<template>
    <BaseSlidePage>
        <div class="slide4__container">
            <div class="slide4__box" v-for="(work, i) in works" :key="i" :style="`background-image:url('${work.img}')`">
                <h4 class="slide4__title">{{ work.title }}</h4>
                <p class="slide4__doc">{{work.doc}}</p>
            </div>
        </div>
    </BaseSlidePage>
</template>

<script>
import BaseSlidePage from '../BaseSlidePage.vue'
import gsap from 'gsap'

export default {
  name: 'Slide4',
  components: {
    BaseSlidePage
  },
  data() {
    return {
        works: [
            {
                title: 'TravelWithUs',
                doc: '金沢市に海外誘致を行うサイトを作成。「IEEE GCCE 2020」で研究成果を発表。',
                img: '/yamaha-interview/images/travelwithus.png'
            },
            {
                title: 'Tourism Project',
                doc: '湯涌町の観光客誘致のためにFlutterによるアプリ開発行う。 現在、自分は当プロジェクトの技術責任者をしています。',
                img: '/yamaha-interview/images/app.png'
            },
            {
                title: 'ホロVRM',
                doc: '趣味で作った作品。iPad上でペッパーズゴースト現状を用いて、そこに居る様に感じることができます。',
                img: '/yamaha-interview/images/AR.png'
            },
            {
                title: '学長召喚Project',
                doc: '左の「ホロAR」を元にそれを巨大化し、等身大の学長の講義をARによって受けることができる。',
                img: '/yamaha-interview/images/学長_AR.png'
            },
            {
                title: 'めしてく',
                doc: '自分のアイデアを友人と一週間開発したウェブサイト。緊急事態宣言下の飲食店のテイクアウト情報をまとめたサイト',
                img: '/yamaha-interview/images/めしてく.png'
            },
            {
                title: 'ホームページ倶楽部',
                doc: '友人の誘いで始めたプロジェクト。Wordpressのテーマの作成を行った。',
                img: '/yamaha-interview/images/nobirurabo.png'
            },
            {
                title: 'Android演習',
                doc: '大学の授業内で作成したAndroidアプリです。SGDsに掲げられる問題解決のアプリをKotlinを用いて開発しました。',
                img: '/yamaha-interview/images/スクリーンショット 2021-04-11 1.00.41.png'
            },
            {
                title: 'バイト DATAGRID',
                doc: '高専の卒研内容を評価してもらい。深層生成モデルの論文実装と開発を行っている。',
                img: '/yamaha-interview/images/dg.png'
            },
            {
                title: '白峰BS',
                doc: '官民学で白峰村をDX化して、教育先端都市にするプロジェクト。自分はオータムキャンプにて３社以上の会社と合同でWebアプリ作成を行った。',
                img: '/yamaha-interview/images/白峰.png'
            },
            {
                title: '趣味の作曲',
                doc: 'プログラミングではないのですが、中学の頃からの趣味。 パソコンを買った理由もこれがきっかけ。 現在も電子計算機部DTM班で作曲継続中',
                img: '/yamaha-interview/images/スクリーンショット 2021-04-11 1.22.17.png'
            },
            {
                title: 'GaKu',
                doc: '高専の授業で作ったWeb上で動くDAW。６人のメンバーで半年かけて作成した。自分はもともとのアイデアとPHPでのバックエンドの実装を行った',
                img: '/yamaha-interview/images/スクリーンショット 2019-07-04 13.29.15.png'
            },
            {
                title: 'ProjectONE!',
                doc: '高専時代に所属していたプロジェクト。JAからの依頼でトマトの収穫量を予測するプログラムの作成を行った。',
                img: '/yamaha-interview/images/1-oH-tJ8WeHZbEU7b-DtJ9uDLEA2clANogqjAjYczeg.png'
            },
            {
                title: '小型植物工場',
                doc: '高専時代に趣味で学校の場所を借りて作っていた水耕栽培マシン。これがきっかけで様々なプロジェクトへの誘いなどもかかった。',
                img: '/yamaha-interview/images/11MG5MuBEvy9vVsUeeVuWApdFe52TXXw8X0i9E2E_Mw.png'
            },
            {
                title: '高専プロコン',
                doc: '高専プログラミングコンテスト競技部門に出場しチームリーダーを勤めた。1勝2敗で敗者復活戦が1勝1敗という結果でした。',
                img: '/yamaha-interview/images/1Ro4_KmATleWZSWohQ64VjsGKckZiJGKq58lnxQkofg.png'
            },
            {
                title: '卒業研究 音声変換',
                doc: '高専時代の卒教研究から初めて、現在の大学の卒業研究でも行っています。',
                img: '/yamaha-interview/images/1XnhJF7tAx3rrg3ztc_IzyWaiwm78pYaySxyIkuxuqQ.png'
            },
        ]
    }
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
      this.addEventScroll('slide4', (rect) => {
        let left =  this.$el.getBoundingClientRect().left - rect.left
        let earlyStartPixcel = window.innerWidth
        console.log(left - earlyStartPixcel);
        if ( left - earlyStartPixcel < 0 ) {
            gsap.from('.slide4__box', {duration: 2, ease: 'Linear.easeNone', opacity: 0, rotation: 360, scale: 0 })
            this.removeEventScroll('slide4')
        }
      })
    }
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
    background-size: cover;
    background-position: center center;
    backdrop-filter: brightness(10%);
    height: calc(100%/3);
    text-align: center;
}
.slide4__container > div::before {
    content: '';
    position: absolute;
    top: 0;
    right: 0;
    left: 0;
    bottom: 0;
    background-color: rgba(0,0,0,0.4);
    z-index: -1;
}
.slide4__title {
    margin: 0;
    padding-top: 13vh;
    padding-bottom: 2vh;
    color: white;
    font-size: 2.2vw;
    text-shadow: 2px 3px 8px rgba(0,0,0,0.3);
}
.slide4__doc {
    color: white;
    font-size: 1vw;
    text-shadow: 1px 0px 5px rgba(0,0,0,0.3);
}
</style>