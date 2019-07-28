<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="area-city">北京</div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="area-city">北京</div>
        <div class="area-city">北京</div>
        <div class="area-city">北京</div>
        <div class="area-city">北京</div>
        <div class="area-city">北京</div>
        <div class="area-city">北京</div>
        <div class="area-city">北京</div>
      </div>
      <div class="area">
        <div class="title border-topbottom">A</div>
        <div class="all-city">阿坝藏族羌族自治州</div>
        <div class="all-city">阿坝藏族羌族自治州</div>
        <div class="all-city">阿坝藏族羌族自治州</div>
        <div class="all-city">阿坝藏族羌族自治州</div>
        <div class="all-city">阿坝藏族羌族自治州</div>
        <div class="all-city">阿坝藏族羌族自治州</div>
        <div class="all-city">阿坝藏族羌族自治州</div>
        <div class="all-city">阿坝藏族羌族自治州</div>
        <div class="all-city">阿坝藏族羌族自治州</div>
      </div>
      <div class="area">
        <div class="title border-topbottom">A</div>
        <div class="all-city">阿坝藏族羌族自治州</div>
        <div class="all-city">阿坝藏族羌族自治州</div>
        <div class="all-city">阿坝藏族羌族自治州</div>
        <div class="all-city">阿坝藏族羌族自治州</div>
        <div class="all-city">阿坝藏族羌族自治州</div>
        <div class="all-city">阿坝藏族羌族自治州</div>
        <div class="all-city">阿坝藏族羌族自治州</div>
        <div class="all-city">阿坝藏族羌族自治州</div>
        <div class="all-city">阿坝藏族羌族自治州</div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CityList',
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .list
    overflow hidden
    position absolute
    top 1.58rem
    left 0
    right 0
    bottom 0
  .title
    line-height .8rem
    background-color #eee
    text-indent .3rem
    font-size .24rem
  .area
    overflow hidden
    .area-city
      box-sizing border-box
      float left
      width 33.3%
      padding .3rem 0
      border .02rem solid #eee
      text-align center
    .all-city
      box-sizing border-box
      float left
      width 25%
      padding .3rem 0
      border .02rem solid #eee
      text-align center
      ellipsis()
</style>
