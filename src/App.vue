<template>
  <div id="app">
    <MyHeader/>

    <MyMain/>
  </div>
</template>

<script>
import axios from 'axios';
import MyHeader from './components/MyHeader.vue';
import MyMain from './components/MyMain.vue';

export default {
  name: 'App',
  components: {
    MyHeader,
    MyMain
  },
  data() {
    return {
      apiUrl: "https://api.themoviedb.org/3/search/movie?api_key=e99307154c6dfb0b4750f6603256716d&query=ritorno+al+futuro",
      films: []
    }
  },
  methods: {
    getFilms() {
      axios
      .get(this.apiUrl)
      .then((film) => {
        this.films = film.data.response;
      })
    }
  }
}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>
