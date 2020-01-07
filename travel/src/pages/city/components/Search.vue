<template>
  <div>
    <div class="search">
      <input type="input" class="search-input" v-model="keyword" placeholder="请输入城市名称或拼音">
  </div>
  <div class="search-content border-bottom" v-show="keyword" ref="ref">
    <ul >
      <li v-for="item in searchList" 
      :key="item.id"
      @click="handleCityClick(item.name)"
      class="search-item border-bottom"
      >
       {{item.name}}</li>
      <li class="search-item border-bottom" v-show="hasNoData">
        没有找到匹配数据
      </li>
    </ul>
  </div>
  </div>
</template>
<script>
import BScroll from 'better-scroll'
import { mapMutations } from 'vuex'
export default {
  name: "CitySearch",
  props:{
    cities:Object
  },
  data() {
    return {
      keyword:'',
      searchList:[],
    }
  },
  computed: {
    hasNoData :function(){
       return !this.searchList.length
    }
  },
  watch: {
    keyword:function(){
      if(!this.keyword){
        this.searchList = []
        return
      }
      const list = []
      for (let cityList in this.cities) {
        this.cities[cityList].forEach(city => {
          if(city.name.indexOf(this.keyword) !=-1 || city.spell.indexOf(this.keyword) !=-1){
            list.push(city)
           }
        });
      }
      this.searchList = list
      
    }
  },
  mounted() {
    this.scroll = new BScroll(this.$refs.ref,{
      click:true
    })
  },
  methods: {
    handleCityClick:function(city){
      this.changeCity(city)
      this.$router.push('/')
  },
  ...mapMutations(['changeCity'])
  },
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
  .search-content
    z-index 1
    overflow hidden
    position absolute
    right 0
    left 0
    top 1.58rem
    bottom 0
    background #eee
    .search-item
      background #fff
      line-height .62rem
      padding-left .2rem
      color #666
      

    
    


 




</style>