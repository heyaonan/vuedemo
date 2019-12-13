<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="swiper in list" :key="swiper.id">
        <img
          class="swiper-img"
          :src="swiper.imgUrl"
        />
      </swiper-slide>
     
      <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
import "swiper/dist/css/swiper.css";
import { swiper, swiperSlide } from "vue-awesome-swiper";
export default {
  name: "HomeSwiper",
  props:{
    list: Array
  },
  data() {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList:[
        {id:'0001',
        imgUrl: 'https://imgs.qunarzz.com/vc/48/4d/58/490ca00c8127e8fe8276ab1a20.jpg_92.jpg'},
           {id:'0002',
        imgUrl: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/201910/abe3418971067bd655fb2794d6e2eeec.jpg'},
           {id:'0003',
        imgUrl: 'https://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20199/76e68eda4ed089c0e5b0ce2367efe428.jpg'}
      ]
    };
  },
  components: {
    swiper,
    swiperSlide
  }
};
</script>
<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active{
  background: #fff
}
.wrapper {
  overflow: hidden;
  width: 100%;
  height: 0;
  padding-bottom: 30.47%;
  background: #eee;

  .swiper-img {
    width: 100%;
  }
}
</style>
