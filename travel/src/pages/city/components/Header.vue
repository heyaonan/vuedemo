<template>
  <div class="header">
    <router-link to="/">
      <div class="iconfont back-icon">&#xe624;</div>
    </router-link>
    城市选择
  </div>
</template>
<script>
export default {
  name: "CityHeader"
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl';
  .header
    position relative
    overflow hidden
    line-height .86rem
    background $bgColor
    text-align center
    color #fff
    font-size .32rem
    .back-icon
      position absolute
      top 0
      left 0
      color #fff
      font-size: .4rem
      width .64rem

</style>