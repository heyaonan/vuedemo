<template>
<div>
  <div class="banner" @click="bannerClick">
    <div class="banner-image">
      <img :src="bannerImg">
    </div>
    <div class="banner-info">
      <div class="info-title">{{ this.sightName }}</div>
      <div class="info-number">
        <span class="iconfont number-icon">&#xe605;</span>
        {{ this.gallaryImgs.length }}</div>
    </div>
  </div>
  <div>
    <fade-animation>
      <common-gallary v-if="isGallary" @close="closeGallary" :images="gallaryImgs"></common-gallary>
    </fade-animation> 
  </div>
</div>
  
</template>
<script>
import CommonGallary from '@/common/gallary/Gallary'
import FadeAnimation from '@/common/fade/FadeAnimation'
export default {
  name: "DetailBanner",
  props:{
    bannerImg: String,
    gallaryImgs: Array,
    sightName: String
  },
  data() {
    return {
      isGallary: false,
    }
  },
  components:{
    CommonGallary,
    FadeAnimation
  },
  methods: {
    closeGallary(){
      this.isGallary = false
    },
    bannerClick(){
      this.isGallary = true
    }
  }
}
</script>
<style lang="stylus" scoped>
  .banner
    position relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img
      width 100%
    .banner-info
      display: flex 
      position: absolute
      bottom 0
      left 0
      right 0
      height .6rem
      line-height .6rem
      color #fff
      background-image: linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8))
      .info-title
        flex 1
        font-size .32rem
        padding 0 .2rem
      .info-number
        padding: 0 .4rem
        height .32rem
        line-height  .32rem
        border-radius .2rem
        background rgba(0,0,0,.8) 
        font-size .2rem
        margin-top .14rem
        .number-icon
         font-size .16rem
  


     
      



</style>
