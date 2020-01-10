<template>
<div class="header">
  <div class="header-title" :style="scrollStyle" v-show="!showAbs">
    <router-link tag="div" to="/" class="header-title-back">
      <div class="iconfont header-fixed-icon">&#xe624;</div>
    </router-link>
    景区详情</div>
  <router-link tag="div" to="/" class="header-back" v-show="showAbs">
    <div class="iconfont header-back-icon">&#xe624;</div>
  </router-link>
</div>
  
  
</template>
<script>
export default {
  name: "DetailHeader",
  data() {
    return {
      scrollStyle:{
        opacity: 0
      },
      showAbs: true
    }
  },
  methods:{
    handleScroll(){
      const scrolltop = document.documentElement.scrollTop
      if(scrolltop  >60){
        let opacity = scrolltop / 140
        opacity = opacity >1 ? 1:opacity
        this.scrollStyle = {
          opacity
        }
        this.showAbs = false
        
      }else{
        this.showAbs = true
      }
      
    }
  },
  activated() {
    window.addEventListener('scroll',this.handleScroll)
  },
  deactivated() {
    window.removeEventListener('scroll',this.handleScroll)
  },
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl';
  .header-title
    top 0
    z-index 2
    position fixed
    line-height .86rem
    background $bgColor
    text-align center
    width 100%
    color #fff
    .header-title-back
      position: absolute
      padding-left .2rem
      top 0
      left 0
      width .64rem
      text-align center
      font-size: .4rem
      color #fff
  .header-back  
    position: absolute
    top: .2rem
    left .2rem
    width .8rem
    height .8rem
    line-height .8rem
    text-align center
    border-radius .4rem
    background #000
    .header-back-icon
      font-size: .4rem
      color #fff

</style>