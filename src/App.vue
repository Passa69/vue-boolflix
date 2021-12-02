<template>
  <div id="app">
    <MyHeader @getInput="setInput" />

    <main>
      <MyMain :films="filmsseries" />
    </main>
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
      apiUrlfilm: "https://api.themoviedb.org/3/search/movie?api_key=e99307154c6dfb0b4750f6603256716d&query=",
      apiUrlseries: "https://api.themoviedb.org/3/search/tv?api_key=e99307154c6dfb0b4750f6603256716d&language=it_IT&query=",
      filmsseries: [],
      search: ""
    }
  },
  methods: {
    getFilms() {
      axios
      .get(this.apiUrlfilm + this.apiUrlseries + this.search)
      .then((film) => {
        this.filmsseries = film.data.results;
        console.log(this.filmsseries);
      })
    },
    setInput(input) {
      this.search = input;
      console.log(input);
      this.getFilms();
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

main {
  background-color: #434343;
}
</style>
