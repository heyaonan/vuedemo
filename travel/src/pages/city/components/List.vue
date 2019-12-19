<template>
<div >
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
          <div class="button-wrapper" v-for="hotcity in hotCityList" :key="hotcity.id">
            <div class="button">{{hotcity.name}} </div>
          </div>
        </div>
      </div>
      <div class="area" v-for="(list, key) in cityList" 
      :key="key"
      :ref="key"
      >
        <div class="title ">{{key}}</div>
        <div class="item-list ">
          <div class="item border-bottom" v-for="(item, index) in list" :key="index">
            {{ item.name }}
          </div>
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
  props:{
    cityList:Object,
    hotCityList: Array,
    letter:String
  },
  mounted() {
    console.log(this.$refs.wrapper)
    this.scroll = new BScroll(this.$refs.wrapper)
  },
  watch: {
    letter:function(){
      if(this.letter){
        this.scroll.scrollToElement(this.$refs[this.letter][0])
      }
      
    }
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
