<template>
  <ul class="list">
    <li class="item" v-for="item of letters"
        :key="item"
        @click="handleLetterClick"
        @touchstart="handleTouchStart"
        @touchmove="handleTouchMove"
        @touchend="handleTouchEnd"
        :ref="item"
    >
      {{item}}
    </li>
  </ul>

</template>

<script>
  export default {
    name: 'CityAlphabet',
    props: {
      cityes: Object
    }, computed: {
      letters() {
        const letters = []
        for (let i in this.cityes) {
          letters.push(i)
        }
        return letters
      }
    }, updated() {
      this.startY = this.$refs['A'][0].offsetTop
    }
    , methods: {
      handleLetterClick(e) {
        this.$emit('change', e.target.innerText)
      },
      handleTouchStart() {
        this.touchStatus = true
      },
      handleTouchMove(e) {
        if (this.touchStatus) {
          if (this.timer) {
            clearTimeout(this.timer)
          }
          this.timer = setTimeout(() => {
            //获取到A距离顶部的高度
            //获取到移动的时候的距离顶部的高度值
            const touchY = e.touches[0].clientY - 79
            const index = Math.floor((touchY - this.startY) / 20)
            if (index >= 0 && index < this.letters.length) {
              this.$emit('change', this.letters[index])
            }
          }, 16)

        }
      },
      handleTouchEnd() {
        this.touchStatus = false
      }
    },
    data() {
      return {
        touchStatus: false,
        startY: 0,
        timer: null
      }
    }
  }

</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"

  .list
    position absolute
    right 0
    top: 1.58rem
    bottom 0
    width .4rem
    display flex
    flex-direction column
    justify-content center
    .item
      text-align center
      line-height .4rem
      color $bgColor

</style>
