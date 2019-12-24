<template>
<div class="header">
  <div class="header-left">
    <div class="iconfont back-icon">&#xe624;</div>
  </div>
  <div class="header-input">
    <span class="iconfont search-icon">&#xe632;</span>
    输入城市/景点/游玩主题
  </div>
  <router-link to="/city">
    <div class="header-right">
      {{city}}
      <span class="iconfont arrow-icon">&#xe600;</span>
    </div>
  </router-link>
</div>
</template>
<script>
export default {
  name:"HomeHeader",
  data() {
    return {
    }
  },
  computed: {
    city:function(){
      return this.$store.state.city
    }
  },
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header
  line-height: 0.86rem
  background: $bgColor
  color: #fff
  display flex
  .header-left
    float left
    width: .64rem
    .back-icon
      font-size: .4rem
      text-align: center
  .header-right
    float: right 
    width: 1.24rem
    text-align: center
    color #fff
    .arrow-icon
      font-size .24rem
      margin-left -.09rem
      margin-top 10.6rem
  .header-input
    flex: 1
    background: #ffffff
    margin-top: .12rem
    margin-left: .2rem
    line-height: .62rem
    height: .62rem
    color: #ccc
    border-radius: .1rem
    padding-left: .2rem
    .search-icon
      font-size .3rem


</style>
