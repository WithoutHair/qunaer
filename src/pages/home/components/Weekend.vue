<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item of list" :key="item.id">
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
  props: {
    list: Array
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
