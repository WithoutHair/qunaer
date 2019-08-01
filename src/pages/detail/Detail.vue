<template>
  <div>
    <DetailBanner></DetailBanner>
    <DetailHeader></DetailHeader>
    <div class="blank">
      <DetailList :list="list"></DetailList>
    </div>
  </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      list: [{
        title: '成人票',
        children: [{
          title: '儿童票',
          children: [{
            title: '学生票'
          }]
        }]
      }, {
        title: '成人票'
      }, {
        title: '成人票'
      }, {
        title: '成人票'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .blank
    height 30rem
</style>
