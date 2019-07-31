<template>
  <div class="container" @click="handleGalleryClose">
    <div class="wrapper">
      <swiper :options="swiperOption">
        <swiper-slide  v-for="(item, index) of imgs" :key="index">
          <img :src="item"/>
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CommonGallery',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observeParents: true,
        observer: true
      }
    }
  },
  props: {
    imgs: {
      type: Array,
      default () {
        return []
      }
    }
  },
  methods: {
    handleGalleryClose () {
      this.$emit('close')
    }
  }
}
</script>

<style lang="stylus" scoped>
  .container
    z-index 99
    display flex
    flex-direction column
    justify-content center
    position fixed
    top 0
    right 0
    bottom 0
    left 0
    background #000
    .wrapper
      width 100%
      height 0
      padding-bottom 100%
      img
        width 100%
    .swiper-pagination
      color #fff
</style>
