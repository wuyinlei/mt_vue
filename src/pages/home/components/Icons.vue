<template>

  <div class="icons">

    <swiper :options="swiperOptionIcon">

      <swiper-slide v-for="(page,index) of pages" :key="index">

        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl"/>
            <p class="icon-desc">{{item.desc}}</p>
          </div>
        </div>
      </swiper-slide>
    </swiper>
  </div>

</template>

<script>
  export default {
    name: "HomeIcons",
    props: {
      iconList: Array
    },
    data() {
      return {
        swiperOptionIcon: {
          loop: false
        }
      }
    },
    computed: {
      pages() {
        const pages = []
        this.iconList.forEach((item, index) => {
          const page = Math.floor(index / 8)
          if (!pages[page]) {
            pages[page] = []
          }
          pages[page].push(item)
        })
        return pages
      }
    }
  }

</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  @import "~styles/mixins.styl"
  .icons >>> .swiper-container
    height 0
    padding-bottom 50%

  .icons
    margin-top .2rem
    .icon
      position relative
      float: left
      width: 25%
      padding-bottom: 25%
      height: 0
      .icon-desc
        bottom 0
        left 0
        right 0
        height .42rem
        line-height .54rem
        color $darkTextColor
        text-align center
        ellipsis()
      .icon-img
        position absolute
        left: 0
        top: 0
        right: 0
        bottom: .46rem
        box-sizing border-box
        padding .1rem
        .icon-img-content
          display: block
          margin: 0 auto
          height: 100%


</style>
