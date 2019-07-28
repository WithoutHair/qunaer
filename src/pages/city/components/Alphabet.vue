<template>
  <ul class="list">
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
  </ul>
</template>

<script>
export default {

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
      line-height .36rem
</style>
