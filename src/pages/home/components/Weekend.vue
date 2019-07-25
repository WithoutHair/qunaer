<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item of WeekendList" :key="item.id">
        <img :src="item.imgUrl">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      WeekendList: [
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1811/f3/86173f863bef61.jpg_r_640x214_52b003ac.jpg',
          title: '京城周末撒欢',
          desc: '在帝都过周末，不仅仅是城中游！'
        }, {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1811/f3/86173f863bef61.jpg_r_640x214_52b003ac.jpg',
          title: '京城周末撒欢',
          desc: '在帝都过周末，不仅仅是城中游！'
        }, {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1811/f3/86173f863bef61.jpg_r_640x214_52b003ac.jpg',
          title: '京城周末撒欢',
          desc: '在帝都过周末，不仅仅是城中游！'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .title
    line-height .8rem
    background-color #eee
    text-indent .3rem
  .item
    img
      width 100%
    .item-info
      padding .24rem
      .item-title
        line-height .54rem
        font-size .3rem
      .item-desc
        line-height .42rem
        font-size .26rem
        color #666
</style>
