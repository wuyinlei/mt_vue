<template>
  <div>
    <home-header>

    </home-header>

    <home-swiper :list="swiperList">

    </home-swiper>

    <home-icons :iconList="iconList">

    </home-icons>

    <home-recommend :recommendList="recommendList">

    </home-recommend>

    <home-weekend :weekendList="weekendList">

    </home-weekend>
  </div>
</template>
<script>
  import HomeHeader from './components/Header'
  import HomeSwiper from './components/swiper'
  import HomeIcons from './components/Icons'
  import HomeRecommend from './components/Recommend'
  import HomeWeekend from './components/Weekend'
  import axios from 'axios'


  export default {
    name: 'Home',
    components: {
      HomeHeader: HomeHeader,
      HomeSwiper: HomeSwiper,
      HomeIcons: HomeIcons,
      HomeRecommend: HomeRecommend,
      HomeWeekend: HomeWeekend
    }, methods: {
      getHomeInfo() {
        axios.get('/api/index.json?city=')
          .then(this.getHomeInfoSucc)
      },
      getHomeInfoSucc(res) {
        res = res.data
        if (res.ret && res.data) {
          const data = res.data;
          this.swiperList = data.swiperList
          this.iconList = data.iconList
          this.recommendList = data.recommendList
          this.weekendList = data.weekendList
        }
      }
    },
    data() {
      return {
        swiperList: [],
        iconList: [],
        recommendList: [],
        weekendList: []
      }
    },
    mounted() {
      this.getHomeInfo()
    },
  }
</script>

<style>

</style>
