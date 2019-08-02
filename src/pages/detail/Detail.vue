<template>
  <div>
    <DetailBanner :sightName="sightName" :bannerImg="bannerImg" :imgs="galleryImgs"></DetailBanner>
    <DetailHeader></DetailHeader>
    <div class="blank">
      <DetailList :list="categoryList"></DetailList>
    </div>
  </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import axios from 'axios'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      lastid: 0,
      sightName: '',
      bannerImg: '',
      galleryImgs: [],
      categoryList: []
    }
  },
  methods: {
    getDetailInfo (id) {
      axios.get('/api/detail.json?id=' + id)
        .then(this.getDetailInfoSucc)
    },
    getDetailInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.galleryImgs = data.gallaryImgs
        this.categoryList = data.categoryList
      }
    }
  },
  mounted () {
    this.lastid = this.$route.params.id
    this.getDetailInfo(this.lastid)
  },
  activated () {
    if (this.$route.params.id !== this.lastid) {
      this.lastid = this.$route.params.id
      this.getDetailInfo(this.lastid)
    }
  }
}
</script>

<style lang="stylus" scoped>
  .blank
    height 30rem
</style>
