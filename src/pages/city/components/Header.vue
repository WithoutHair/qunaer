<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <div class="iconfont header-back">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    position relative
    height .86rem
    line-height .86rem
    text-align center
    background $bgColor
    font-size .34rem
    color #fff
    .header-back
      position absolute
      top 0
      left .1rem
      font-size .4rem
      color #fff
</style>
