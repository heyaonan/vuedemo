<template>
  <div>
    <detail-banner :bannerImg="bannerImg" :gallaryImgs="gallaryImgs" :sightName="sightName"></detail-banner>
    <detail-header></detail-header>
    <detail-list :list="categoryList"></detail-list>
  </div>
</template>
<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import axios from 'axios'

export default {
  name: "Detail",
  data() {
    return {
      bannerImg: '',
      categoryList:[],
      gallaryImgs: [],
      sightName: ''
    }
  },
  methods:{
    getDetailInfo(){
      axios.get('/api/detail.json?id='+ this.$route.params.id)
        .then(this.getDetailInfoSucc)
    },
    getDetailInfoSucc(res){
      res = res.data
      if(res.ret && res.data ){
        const data = res.data
        this.bannerImg = data.bannerImg
        this.categoryList = data.categoryList
        this.gallaryImgs = data.gallaryImgs
        this.sightName = data.sightName
      }
    }
  },
  activated() {
    this.getDetailInfo();
  },
  components:{
    DetailBanner,
    DetailHeader,
    DetailList
  }
}
</script>
