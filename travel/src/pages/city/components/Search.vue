<template>
  <div class="search">
      <input type="input" class="search-input" placeholder="请输入城市名称或拼音">
  </div>
</template>
<script>
export default {
  name: "CitySearch"
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl';
  .search
    padding 0 .1rem
    height .72rem
    background $bgColor
    .search-input
      box-sizing border-box
      width 100% 
      line-height .62rem
      height .62rem
      text-align center
      border-radius .06rem    
      padding 0 .1rem  
      color #666
 




</style>