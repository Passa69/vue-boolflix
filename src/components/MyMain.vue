<template>
  <main>
    <div v-for="(movie, i) in films" :key="i">
        <!-- immagine -->
        <img :src="'http://image.tmdb.org/t/p/w500/' + movie.poster_path" alt="">

        <!-- Titolo -->
        <h4 class="film_element">{{ movie.title }}</h4>
        <h4 v-if="movie.name" class="film_element">{{ movie.name }}</h4>

        <!-- Titolo Originale -->
        <h5 class="film_element">{{ movie.original_title }}</h5>
        <h5 v-if="movie.original_name" class="film_element">{{ movie.original_name }}</h5>

        <!-- Lingua -->
        <p class="film_element" v-if="movie.original_language === 'it'">&#127470;&#127481;</p>
        <p class="film_element" v-else-if="movie.original_language === 'en'">&#127988;&#917607;&#917602;&#917605;&#917614;&#917607;&#917631;</p>
        <p class="film_element" v-else>&#127987;&#65039;&#8205;&#127752;</p>

        <!-- Voto -->
        <p class="film_element">{{ movie.vote_average }}</p>
    </div>
  </main>
</template>

<script>
export default {
  name: 'MyMain',
  props: {
      films: Array
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
main {
    height: 100%;
    margin: 0 auto;
    width: 80%;
    display: flex;
    flex-wrap: wrap;
}

div{
    // height: 400px;
    // width: 300px;
    background-color: #b1dbec;
    margin: 50px;
}

.film_element {
    margin-bottom: 10px;
}
</style>