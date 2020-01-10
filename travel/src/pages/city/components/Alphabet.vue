<template>
  <ul class="alphabet">
    <li 
    v-for="item in letters"
    :key="item"
    @click="handleLetterClick"
    @touchstart.prevent="handleTouchStart"
    @touchmove="handleTouchMove"
    @touchend="handleTouchEnd"
    :ref="item"
    >{{ item }}</li>
  </ul>
</template>
<script>
export default {
  name: "CityAlphabet",
  props:{
    cityList: Object
  },
  data() {
    return {
      touchStatus: false,
      startY: 0,
      timer:null
    }
  },
  updated (){
    this.startY = this.$refs['A'][0].offsetTop
  },
  computed: {
    letters:function(){
      let letters = []
      for(let i in this.cityList){
        letters.push(i)
      }
      return letters
    }
  },
  methods:{
    handleLetterClick:function(e){
      this.$emit('change',e.target.innerText)
    },
    handleTouchStart:function (){
      this.touchStatus = true
    },
    handleTouchMove:function (e){
      if(this.touchStatus){
        if(this.timer){
          clearTimeout(this.timer)
        }
        setTimeout(()=>{
          const touchY = e.touches[0].clientY - 79
          const index = Math.floor((touchY - this.startY) / 20)
          this.$emit('change',this.letters[index])
        },16)
       
      }
    },
    handleTouchEnd:function (){
      this.touchStatus = false
    },

  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl';
  .alphabet 
    display flex
    flex-direction column
    position absolute
    top 1.58rem
    right 0.1rem
    bottom 0
    justify-content: center
    li
      color $bgColor
      text-align center
      line-height .4rem
</style>