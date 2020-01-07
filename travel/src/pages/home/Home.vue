<template>
  <div>
    <home-header :city="city"></home-header>
    <home-swiper :list="swiperList"></home-swiper>
    <home-icons :list="iconList"></home-icons>
    <home-recommend :list="recommendList"></home-recommend>
    <home-weekend :list="weekendList"></home-weekend>
  </div>
</template>
<script>
import HomeHeader from "./components/Header";
import HomeSwiper from "./components/Swiper";
import HomeIcons from "./components/Icons";
import HomeRecommend from "./components/Recommend";
import HomeWeekend from "./components/Weekend";
import axios from "axios"
import { mapState } from "vuex"

export default {
  name: "Home",
  data() {
    return {
      iconList:[],
      swiperList:[],
      recommendList:[],
      weekendList:[],
      swiperList:[],
      lastyCity: ''
    };
  },
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  computed:{
    ...mapState(['city'])
  },
  methods: {
    getHomeInfo(){
      axios.get('/api/index.json?city='+this.city)
        .then(this.getHomeInfotSucc)
    },
    getHomeInfotSucc(res){
       res = res.data
      if(res.ret && res.data){
        const data = res.data
        this.iconList = data.iconList
        this.recommendList = data.recommendList
        this.weekendList = data.weekendList
        this.swiperList = data.swiperList
      }
      console.log(res)
    }

  },
  mounted() {
    console.log('mouted')
    this.lastyCity = this.city
    this.getHomeInfo()
  },
  activated(){
    console.log('activated')
    if(this.lastyCity !== this.city){
      this.lastyCity = this.city
      this.getHomeInfo()
    }
   
  }
};
</script>
<style scoped>
</style>
