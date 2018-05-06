<template>

  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">{{this.currentCity}}</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper"
               v-for="item of hotCities"
               :key="hotCities.id"
               @click="handleCityClick(item.name)"
          >
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>

      <div class="area" v-for="(item,key) of cityes"
           :key="key"
           :ref="key"
      >
        <div class="title border-topbottom">{{key}}</div>
        <div class="item-list">
          <div class="item border-bottom"
               v-for="innerItem of item"
               :key="innerItem.id"
               @click="handleCityClick(innerItem.name)"
          >
            {{innerItem.name}}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import BScroll from 'better-scroll'
  import {mapState,mapMutations} from 'vuex'

  export default {
    name: 'CityList',
    mounted() {
      this.scroll = new BScroll(this.$refs.wrapper)
    },
    computed:{
      //mapState是指把vuex里面的数据映射到这个组件的computed的计算属性里面  也就是把city这个数据映射到
      ...mapState({
        currentCity:'city'
      })
    },
    watch: {
      letter() {
        if (this.letter) {
          const element = this.$refs[this.letter][0]
          this.scroll.scrollToElement(element)
        }
      }
    },
    methods: {
      handleCityClick(city) {
        // this.$store.commit('changeCity', city)
        this.changeCity(city),
        this.$router.push('/')
      },
      ...mapMutations(['changeCity'])
    },
    props: {
      hotCities: Array,
      cityes: Object,
      letter: String
    }
  }
</script>

<style lang="stylus" scoped>

  .border-topbottom
    &:before
      border-color #ccc
    &:after
      border-color #ccc

  .border-bottom
    &:before
      border-color #ccc

  .list
    overflow hidden
    position absolute
    top 1.58rem
    bottom 0
    left 0
    right 0
    .title
      line-height .54rem
      font-size .26rem
      background #f4f4f4
      padding-left .2rem
      color #666
    .button-list
      padding .1rem .6rem .1rem .1rem
      overflow hidden
      .button-wrapper
        float left
        width 33.33%
        .button
          text-align center
          margin .1rem
          padding .1rem 0
          border .02rem solid #ccc
          border-radius .06rem
    .item-list
      .item
        line-height .76rem
        color #666
        padding-left .2rem


</style>
