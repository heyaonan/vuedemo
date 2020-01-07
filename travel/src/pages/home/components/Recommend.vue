<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
        <router-link 
          tag="li"
          class="item border-bottom" 
          v-for="item in list" 
          :key="item.id"
          :to="'/detail/'+item.id">
        <img class ="item-img" :src="item.imgUrl">
        <div class="item-info ">
          <p class="item-title">{{ item.title }}</p>
          <p class="item-desc">{{ item.desc }}</p>
          <button class="item-button">详情信息</button>
        </div>
      </router-link>
      
      
    </ul>
  </div>
</template>
<script>
export default {
  name: "HomeRecommend",
  props:{
    list: Array
  },
  data() {
    return {
      
    }
  },
}
</script>
<style lang="stylus" scoped>
@import '~styles/mixin.styl';
.title
  line-height .8rem
  background #eeeeee
  margin-top .2rem
  text-indent .2rem
.item
  overflow hidden
  display flex
  height 1.9rem
  .item-img
    width 1.7rem
    height 1.7rem
    padding .1rem
  .item-info
    flex 1
    min-width 0
    padding .1rem
    .item-title
      ellipsis()
      line-height .54rem
      font-size .32rem
    .item-desc
      ellipsis()
      line-height .4rem
      color #ccc
    .item-button
      margin-top .2rem
      background #ff9300
      padding 0 .2rem
      color #fff
      border-radius .06rem
      line-height .44rem


</style>