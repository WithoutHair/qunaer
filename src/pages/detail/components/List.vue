<template>
  <div>
    <div class="item border-bottom" v-for="(item, index) of list" :key="index">
      {{item.title}}
      <div class="children" v-if='item.children'>
        <DetailList :list="item.children"></DetailList>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  .item
    line-height .6rem
    font-size .3rem
    padding-left .1rem
    .children
      padding-left .2rem
</style>
