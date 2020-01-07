<template>
  <div class="banner">
    <div class="banner-image">
      <img src="https://imgs.qunarzz.com/sight/p0/2001/85/85d9988db74c3a90a3.water.jpg_710x360_847a0cc1.jpg">
    </div>
    <div class="banner-info">
      <div class="info-title">珠海长隆度假村野生动物园欢迎您</div>
      <div class="info-number">
        <span class="iconfont number-icon">&#xe605;</span>
        39</div>
    </div>
  </div>
</template>
<script>
export default {
  name: "DetailBanner",
  data() {
    return {
      
    }
  },
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
