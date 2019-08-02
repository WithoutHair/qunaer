<template>
  <div>
    <div class="banner" @click="handleShowGallery">
      <img class="banner-img" :src="bannerImg" >
      <div class="banner-title">{{this.sightName}}</div>
      <div class="banner-info">
        <span class="iconfont banner-icon">&#xe757;</span>
        <span>10</span>
      </div>
      <div class="banner-gradient"></div>
    </div>
    <CommonGallery @close="handleGalleryClose" :imgs="imgs" v-show="showGallery"></CommonGallery>
  </div>
</template>

<script>
import CommonGallery from 'common/gallery/Gallery'
export default {
  name: 'DetailBanner',
  data () {
    return {
      showGallery: false
    }
  },
  props: {
    sightName: String,
    bannerImg: String,
    imgs: Array
  },
  components: {
    CommonGallery
  },
  methods: {
    handleShowGallery () {
      this.showGallery = true
    },
    handleGalleryClose () {
      this.showGallery = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position relative
    overflow hidden
    height 0
    padding-bottom 55%
    color #fff
    .banner-img
      width 100%
    .banner-title
      position absolute
      top auto
      right auto
      bottom .4rem
      left .2rem
      font-size .36rem
    .banner-info
      box-sizing border-box
      position absolute
      top auto
      right auto
      bottom .9rem
      left .24rem
      padding .08rem .32rem
      border-radius .2rem
      background rgba(0, 0, 0, .4)
      font-size .24rem
      .banner-icon
        font-size .26rem
    .banner-gradient
      position absolute
      bottom 0
      width 100%
      min-height .5rem
      background linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, .8))
</style>
