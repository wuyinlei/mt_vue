<template>
  <div class="header">
    <div class="header-finish">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>输入城市/景点/游园/主题
    </div>
    <router-link to="/city">
      <div class="header-location">
        {{this.city}}
        <span class="iconfont arrow-icon">&#xe64a;</span></div>
    </router-link>

  </div>
</template>
<script>
  import {mapState} from 'vuex'
  export default {
    name: 'HomeHeader',
    computed:{
      //mapState是指把vuex里面的数据映射到这个组件的computed的计算属性里面  也就是把city这个数据映射到
      ...mapState(['city'])
    }
  }
</script>
<!--这里试用scoped来限定使用范围  不会对其他有印象-->
<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  .header
    line-height: $headerHeight
    display flex
    background $bgColor
    color: #fff
    .header-finish
      width: 0.64rem
      float: left
      .back-icon
        text-align: center
        font-size 0.4rem
    .header-input
      flex: 1
      height: 0.64rem
      line-height: 0.64rem
      background #ffffff
      border-radius 0.1rem
      margin-top: 0.12rem
      margin-left: .2rem
      padding-left: 0.2rem
      color: #ccc
    .header-location
      padding 0 .1rem
      min-width: 1.04rem
      float: right
      text-align center
      color white
      .arrow-icon
        font-size: 0.24rem

</style>
