<template>
  <header-view></header-view>
  <main-visual></main-visual>
  <tab-content></tab-content>
  <ani-view></ani-view>
  <swiper-view :sData="sData"></swiper-view>
  <recruit-view :rData="rData"></recruit-view>
  <footer-view></footer-view>
</template>

<script>
// components
import HeaderView from './components/HeaderView.vue'
import MainVisual from './components/MainVisual.vue'
import TabContent from './components/TabContent.vue'
import AniView from './components/AniView.vue'
import SwiperView from './components/SwiperView.vue'
import RecruitView from './components/RecruitView.vue'
import FooterView from './components/FooterView.vue'

// data
import sData from '@/data/04swiperView.js'
import rData from '@/data/05RecruitView.js'


export default {
  components: {
    HeaderView,
    MainVisual,
    TabContent,
    AniView,
    SwiperView,
    RecruitView,
    FooterView
    },
    data(){
      return{
        sData:sData,
        rData:rData,
      }
    }

}
</script>

<style>
@import url(./assets/style.css);
</style>