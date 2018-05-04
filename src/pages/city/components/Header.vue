<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <div class="iconfont back-icon">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
  export default {
    name: 'CityHeader'
  }
</script>

<style lang="stylus" scoped>

  @import "~styles/varibles.styl"

  .header
    line-height: $headerHeight
    position relative
    background $bgColor
    font-size .32rem
    line-height $headerHeight
    text-align center
    color: #fff

    .back-icon
      position absolute
      top 0
      left .2rem
      text-align: center
      font-size 0.4rem
      color white

</style>
