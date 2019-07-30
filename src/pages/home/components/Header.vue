<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        <span class="city">{{this.city}}</span>
        <span class="iconfont choice">&#xe64a;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city'])
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .header
    display flex
    line-height .86rem
    background $bgColor
    color #fff
    .header-left
      width .64rem
      float left
      div
        text-align center
        font .4rem
    .header-input
      flex 1
      height .64rem
      line-height .64rem
      margin .12rem 0 0 .2rem
      padding-left .15rem
      border-redius .1rem
      background #fff
      color #ccc
    .header-right
      width 1.24rem
      float right
      text-align center
      color #fff
      .city
        display inline-block
        max-width .56rem
        vertical-align middle
        font-size .28rem
        ellipsis()
      .choice
        font-size .24rem
</style>
