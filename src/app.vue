<template>
  <div id="app">
    <button type="button" @click="searchWeather">보기</button>
    <div v-if='view === true'>
      <h2>국가명 : {{ country }}</h2>
      <p>도시명 : {{ city }}</p>
    </div>
  </div>
</template>

<script>
import { posix } from 'path';
export default {
  name: 'app',
  data() {
    return {
      view: false,
      country: '',
      city: ''
    }
  },
  computed: {
      hasResult: function() {
        return this.posts.length > 0
      }
  },
  methods: {
    searchWeather() {
      const BASE_URL = 'https://samples.openweathermap.org/data/2.5/weather?q=London,uk&appid=439d4b804bc8187953eb36d2a8c26a02'
      this.$http.get(`${BASE_URL}`)
      .then((result) => {
        this.country = result.data.sys.country
        this.city = result.data.name
        this.view = true
        console.log(result)
      })
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
