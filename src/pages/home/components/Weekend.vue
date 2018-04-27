<template>
  <div>
    <div class="title border-top">周末游</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">


        <div>
          <img class="item-img"
               :src="item.imgUrl"/>
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>

      <li class="click-look-more  border-bottom">
        点击查看更多
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: 'Recommend',
    data() {
      return {
        recommendList: [
          {
            "id": "0001",
            "imgUrl": "http://imgs.qunarzz.com/p/p48/201302/28/bc44faa497db0dcf93835fbb.jpg_256x160_0ba13461.jpg",
            "title": "北京蓝田玉烟别墅你值得拥有哈哈",
            "desc": "北京昌平区天通苑北王府花园"
          },
          {
            "id": "0002",
            "imgUrl": "http://imgs.qunarzz.com/p/p48/201302/28/bc44faa497db0dcf93835fbb.jpg_256x160_0ba13461.jpg",
            "title": "北京蓝田玉烟别墅我已经有了你信么，我不信",
            "desc": "北京昌平区天通苑北王府花园"
          },
          {
            "id": "0003",
            "imgUrl": "http://imgs.qunarzz.com/p/p48/201302/28/bc44faa497db0dcf93835fbb.jpg_256x160_0ba13461.jpg",
            "title": "北京蓝田玉烟别墅",
            "desc": "北京昌平区天通苑北王府花园"
          },
          {
            "id": "0004",
            "imgUrl": "http://imgs.qunarzz.com/p/p48/201302/28/bc44faa497db0dcf93835fbb.jpg_256x160_0ba13461.jpg",
            "title": "北京蓝田玉烟别墅",
            "desc": "北京昌平区天通苑北王府花园"
          },
          {
            "id": "0005",
            "imgUrl": "http://imgs.qunarzz.com/p/p48/201302/28/bc44faa497db0dcf93835fbb.jpg_256x160_0ba13461.jpg",
            "title": "北京蓝田玉烟别墅",
            "desc": "北京昌平区天通苑北王府花园"
          },
        ]
      }
    }
  }
</script>

<style lang="stylus" scoped>
  @import "~styles/mixins.styl"
  .title
    line-height .8rem
    background #fff
    text-indent .2rem

  .item
    height 0
    overflow hidden
    padding-bottom 58%
    .item-img
      width 100%
      height 3rem
      padding .1rem

    .item-title
      line-height .54rem
      font-size .32rem
      padding-left .1rem
      ellipsis()
    .item-desc
      line-height .4rem
      font-size .28rem
      padding-left .1rem
      color #ccc
      ellipsis()


  .click-look-more
    line-height .8rem
    background #fff
    text-indent .2rem
    text-align center
    color #ff9300
    font-size .34rem


</style>
