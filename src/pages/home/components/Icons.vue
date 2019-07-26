<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon-img" v-for="item of page" :key="item.id">
          <div class="icon-img-content">
          <img :src="item.imgUrl">
          </div>
          <p>{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      swiperOption: {
        loop: false
      }
    }
  },
  props: {
    list: Array
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .icons
    height 0
    padding-bottom 50%
    .icon-img
      position relative
      float left
      width 25%
      height 0
      padding-bottom 25%
      .icon-img-content
        position absolute
        top 0
        right 0
        left 0
        bottom .44rem
        box-sizing border-box
        padding .1rem
        img
          display block
          height 100%
          margin 0 auto
      p
        position absolute
        right 0
        bottom 0
        left 0
        text-align center
        height .44rem
        line-height .44rem
        color $darkTextColor
        ellipsis()
</style>
