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

export default {
  name: "Home",
  data() {
    return {
      city: "",
      iconList:[],
      swiperList:[],
      recommendList:[],
      weekendList:[],
      swiperList:[]
    };
  },
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  methods: {
    getHomeInfo(){
      axios.get('/api/index.json')
        .then(this.getHomeInfotSucc)
    },
    getHomeInfotSucc(res){
       res = res.data
      if(res.ret && res.data){
        const data = res.data
        this.city = data.city
        this.iconList = data.iconList
        this.recommendList = data.recommendList
        this.weekendList = data.weekendList
        this.swiperList = data.swiperList
      }
      console.log(res)
    }

  },
  mounted() {
    this.getHomeInfo()
  },
};
</script>
<style scoped>
</style>
