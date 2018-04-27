<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <img class="item-img"
             :src="item.imgUrl"/>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>

      <div class="click-look-more">
        点击查看更多
      </div>
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
    margin-top .2rem
    line-height .8rem
    background #fff
    text-indent .2rem


  .item
    display flex
    height 1.9rem
    overflow hidden
    .item-img
      width 2.4rem
      height 1.7rem
      padding .1rem
    .item-info
      flex 1
      min-width 0
      padding .1rem
      .item-title
        line-height .54rem
        font-size .32rem
        ellipsis()
      .item-desc
        line-height .4rem
        font-size .28rem
        color #ccc
        ellipsis()
      .item-button
        line-height .14rem
        margin-top .16rem
        color #ffffff
        background #ff9300
        padding 0.2rem
        border-radius .06rem

  .click-look-more
    line-height .8rem
    background #fff
    text-indent .2rem
    text-align center
    color #ff9300
    font-size .34rem


</style>
