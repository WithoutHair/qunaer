<template>
  <div>
    <router-link tag="div" to="/" class="header-abs iconfont" v-show="showAbs">&#xe624;</router-link>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
      <router-link tag="div" to="/" class="header-back iconfont">&#xe624;</router-link>
      <div class="header-text">景点详情</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleFixedShow () {
      const top = document.documentElement.scrollTop
      if (top > 56) {
        let opacity = top / 164
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleFixedShow)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleFixedShow)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header-abs
    position absolute
    top .2rem
    left .2rem
    width .8rem
    height .8rem
    line-height .8rem
    text-align center
    border-radius .4rem
    background rgba(0, 0, 0, .4)
    color #fff
  .header-fixed
    z-index 2
    position fixed
    top 0
    right 0
    left 0
    line-height $headerHeight
    background-color $bgColor
    color #fff
    font-size .34rem
    .header-text
      text-align center
    .header-back
      position absolute
      left .1rem
</style>
