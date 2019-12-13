<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) in pages" :key="index">
        <div class="icon" v-for="(icon, index) in page" :key="index">
          <div class="icon-img">
            <img class="icon-img-content" :src="icon.imgUrl" />
          </div>
          <p class="icon-desc">{{ icon.desc }}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>
<script>
export default {
  name: "HomeIcons",
  props:{
    list: Array
  },
  data() {
    return {
      swiperOption:{
        pagination:".swiper-pagination",
        autoPlay: false
      }
    };
  },
  computed: {
    pages: function() {
      const pages = [];
      this.list.forEach((icon,index) => {
        const page = Math.floor(index / 8);
        if (!pages[page]) {
          pages[page] = [];
        }
        pages[page].push(icon);
      });
      return pages;
    }
  }
};
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl';
@import '~styles/mixin.styl'
.icons >>> .swiper-container {
  height: 0;
  padding-bottom: 50%;

  .icon {
    overflow: hidden;
    height: 0;
    width: 25%;
    padding-bottom: 25%;
    float: left;
    position: relative;

    .icon-img {
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0.44rem;
      box-sizing: border-box;
      padding: 0.2rem;

      .icon-img-content {
        display: block;
        margin: 0 auto;
        height: 100%;
      }
    }

    .icon-desc {
      position: absolute;
      left: 0;
      right: 0;
      bottom: 0;
      line-height: 0.44rem;
      height: 0.44rem;
      text-align: center;
      color: $darkTextColor;
      ellipsis()
    }
  }
}
</style>