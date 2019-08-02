<template>
  <div>
    <div class="title">猜你喜欢</div>
    <ul>
      <router-link tag="li" class="item border-bottom" v-for="item of list" :key="item.id" :to="'/detail/' + item.id">
        <img class="item-img" :src="item.imgUrl">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeReco',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
    margin-top .2rem
    text-indent .3rem
    line-height .8rem
    background #eee
  .item
    height 1.9rem
    overflow hidden
    display flex
    .item-img
      width 1.7rem
      height 1.7rem
      padding .1rem
    .item-info
      flex 1
      padding .1rem
      .item-title
        line-height .54rem
        font-size .32rem
      .item-desc
        line-height .4rem
        color #bbb
        ellipsis()
      .item-button
        margin-top .1rem
        padding 0 .2rem
        line-height .44rem
        background-color #ff9300
        color #fff
        border-radius .1rem
</style>
