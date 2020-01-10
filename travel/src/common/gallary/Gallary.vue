<template>
  <div class="container" @click="handleGallaryClick">
    <div class="wrapper">
      <swiper :options="swiperOption">
      <swiper-slide v-for="(image, index) in images" :key="index">
        <img class="gallary-img" :src="image">
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
    </div>
  </div>
</template>
<script>
export default {
  name: "CommonGallary",
  props:{
    images: {
      type: Array,
      default (){
        return{}
      }
    }
  },
  data() {
    return {
      swiperOption:{
        pagination : '.swiper-pagination',
        paginationType : 'fraction',
        observeParents: true,
        observer: true
      }
    }
  },
  methods:{
    handleGallaryClick(){
      this.$emit('close')
    }
  }
}
</script>
<style lang="stylus" scoped>
.container >>> .swiper-container
    overflow: inherit
.container
  display flex
  flex-direction column
  justify-content center
  z-index 99
  top 0
  right 0
  left 0
  bottom 0
  position: fixed
  background #000
  .wrapper
    height 0
    width 100%
    padding-bottom 100%
    .gallary-img
      width 100%
    .swiper-pagination
      color #ffffff
      bottom -1rem


</style>