<template>
  <ul class="list">
    <li class="item" v-for="(item, key) of cities" :key="key">{{key}}</li>
  </ul>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .list
    display flex
    width .2rem
    flex-direction column
    justify-content center
    position absolute
    top 0
    right .05rem
    bottom 0
    text-align center
    color $bgColor
    .item
      line-height .4rem
</style>
