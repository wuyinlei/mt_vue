<template>
  <div class="wrapper">
    <swiper :options="swiperOption">

      <!-- slides -->
      <swiper-slide v-for="item of swiperList" :key="item.id">


        <img class="swiper-image" :src="item.imgUrl"/>


      </swiper-slide>

      <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination"></div>

    </swiper>


  </div>
</template>

<script>

  export default {
    name: 'HomeSwiper',
    data() {
      return {
        swiperOption: {
          autoplay: 5000,
          // initialSlide: 1,
          loop: true,
          pagination: '.swiper-pagination',
        },
        swiperList: [
          {
            "id": '0001',
            "imgUrl": "http://p0.meituan.net/codeman/33ff80dc00f832d697f3e20fc030799560495.jpg"
          },
          {
            "id": '00021',
            "imgUrl": "http://p1.meituan.net/codeman/5296b8d76dc6c2e484def2e22ce0595b197829.jpg"
          },
          {
            "id": '0003',
            "imgUrl": "http://p1.meituan.net/codeman/826a5ed09dab49af658c34624d75491861404.jpg"
          }]
      }
    },
  }
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff

  .wrapper
    width 100%
    height 0
    overflow hidden
    padding-bottom 31.25%
    background #ccc
    .swiper-image
      width: 100%

</style>
