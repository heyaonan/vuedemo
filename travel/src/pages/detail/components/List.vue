<template>
<div class="item">
  <div class="item-title border-bottom" v-for="(item,index) in list" :key="index">
    <span class="item-title-icon"></span>
     {{ item.title }}
     <div v-if="item.children">
       <detail-list :list="item.children"></detail-list>
     </div>
  </div>
</div>
  
  
</template>
<script>
export default {
  name: "DetailList",
  props:{
    list:Array
  },
  data() {
    return {
      
    }
  },
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl';
.item
  line-height .8rem
  padding-left .3rem
  .item-title-icon
    position: relative
    left: .06rem
    top: .06rem
    display: inline-block
    width: .36rem
    height: .36rem
    background: url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat
    margin-right: .1rem
    background-size: .4rem 3rem


</style>