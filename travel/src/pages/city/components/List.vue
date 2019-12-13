<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">上海</div>
          </div>
          <div class="button-wrapper">
            <div class="button">广州</div>
          </div>
          <div class="button-wrapper">
            <div class="button">深圳</div>
          </div>
          <div class="button-wrapper">
            <div class="button">西安</div>
          </div>
          <div class="button-wrapper">
            <div class="button">成都</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title ">A</div>
        <div class="item-list ">
          <div class="item border-bottom">
            阿坝
          </div>
           <div class="item border-bottom">
            阿拉善
          </div>
           <div class="item border-bottom">
            阿克苏
          </div>
           <div class="item border-bottom">
            阿里
          </div>
           <div class="item border-bottom">
            阿勒泰
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title ">B</div>
        <div class="item-list ">
          <div class="item border-bottom">
            北京
          </div>
           <div class="item border-bottom">
            包头
          </div>
           <div class="item border-bottom">
            北海
          </div>
           <div class="item border-bottom">
            北流
          </div>
           <div class="item border-bottom">
            白山
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'CityList',
  mounted() {
    this.scroll = new BScroll(this.$refs.wrapper)
  },
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .border-topbottom
    &:before
      border-color: #ccc
    &:after
      border-color: #ccc
  .border-bottom
    &:before
      border-color: #ccc
  .list
    overflow: hidden
    position: absolute
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    .title
      line-height: .54rem
      background: #eee
      padding-left: .2rem
      color: #666
      font-size: .26rem
    .button-list
      overflow hidden
      padding .1rem .6rem .1rem .1rem
      .button-wrapper
        float left
        width 33.3%
        .button
          padding .1rem
          margin .1rem
          border .02rem solid #ccc
          text-align center
          border-radius .06rem
    .item-list
      .item
        line-height: .76rem
        padding-left: .2rem
</style>
