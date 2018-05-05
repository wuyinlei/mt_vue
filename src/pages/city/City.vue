<template>

  <div>

    <city-header>
    </city-header>

    <city-search>

    </city-search>

    <city-list :letter="letter" :cityes="cityes" :hotCities="hotCities">

    </city-list>

    <city-alphabet @change='handlerLetterChange' :cityes="cityes">

    </city-alphabet>
  </div>


</template>

<script>
  import CityHeader from './components/Header'
  import CitySearch from './components/Search'
  import CityList from './components/List'
  import CityAlphabet from './components/Alphabet'
  import axios from 'axios'


  export default {
    name: 'City',
    components: {
      CityList,
      CityHeader,
      CitySearch,
      CityAlphabet
    }, methods: {
      getCityInfo() {
        axios.get('/api/city.json')
          .then(this.getCityInfoSucc)
      },
      getCityInfoSucc(res) {
        res = res.data
        if (res.ret && res.data) {
          const data = res.data;
          this.hotCities = data.hotCities
          this.cityes = data.cities
        }
      },
      handlerLetterChange(letter) {
        this.letter = letter
      }
    },
    data() {
      return {
        hotCities: [],
        cityes: {},
        letter: ''
      }
    },
    mounted() {
      this.getCityInfo()
    }
  }
</script>

<style lang="stylus" scoped>

</style>
