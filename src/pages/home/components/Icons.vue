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
      },
      iconList: [
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          desc: '景点门票'
        }, {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/6c/9e54a8540fee0102.png',
          desc: '故宫'
        }, {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
          desc: '北京必游'
        }, {
          id: '0004',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/3e/86314b2af03b7502.png',
          desc: '水上乐园'
        }, {
          id: '0005',
          imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20191/0334cf5430b9b5505fd79e2b8d7e8670.png',
          desc: '爬长城'
        }, {
          id: '0006',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/67/9a1678221b8e0e02.png',
          desc: '古北水镇'
        }, {
          id: '0007',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
          desc: '动植物园'
        }, {
          id: '0008',
          imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/b4511345827006994aa1980a3886f0ac.png',
          desc: '北京世园会'
        }, {
          id: '0009',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/87/a6521252870ea402.png',
          desc: '考生专享'
        }
      ]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
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
