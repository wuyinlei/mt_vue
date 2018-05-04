<template>
  <div>
    <div class="title border-top">周末游</div>
    <ul>
      <li class="item border-bottom" v-for="item of weekendList" :key="item.id">


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
    props: {
      weekendList: Array
    },
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
