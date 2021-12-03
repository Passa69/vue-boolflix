<template>
  <main>
    <div v-for="(movie, i) in films" class="film" :key="i">
        <!-- immagine -->
        <img v-if="movie.poster_path === null" class="netflix_path" :src="'http://www.losbagliato.it/wp-content/uploads/2021/07/copertina-netflix-23-giugno-960x960.png'" alt="">
        <img v-else :src="'http://image.tmdb.org/t/p/w500/' + movie.poster_path" alt="">

        <div class="film_description">
          <!-- Titolo -->
          <h4 class="film_element"><strong>Titolo:</strong> {{ movie.title }}</h4>
          <h4 v-if="movie.name" class="film_element"><strong>Titolo:</strong> {{ movie.name }}</h4>

          <!-- Titolo Originale -->
          <h5 class="film_element"><strong>Titolo Originale:</strong> {{ movie.original_title }}</h5>
          <h5 v-if="movie.original_name" class="film_element"><strong>Titolo Originale:</strong> {{ movie.original_name }}</h5>

          <!-- Lingua -->
          <p class="film_element" v-if="movie.original_language === 'it'"><strong>Lingua:</strong> &#127470;&#127481;</p>
          <p class="film_element" v-else-if="movie.original_language === 'en'"><strong>Lingua:</strong> &#127988;&#917607;&#917602;&#917605;&#917614;&#917607;&#917631;</p>
          <p class="film_element" v-else><strong>Lingua:</strong> &#127987;&#65039;&#8205;&#127752;</p>

          <!-- Voto -->
          <p class="film_element"><strong>Voto:</strong> <font-awesome-icon icon="star" class="checked" /> <font-awesome-icon icon="star" /> {{ movie.vote_average/2 }}</p>

          <!-- Trama -->
          <p class="film_plot"><strong>Trama:</strong> {{ movie.overview }}</p>
        </div>        
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

.film {
  margin: 50px;
  position: relative;
}

.film_description {
  display: none;
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  padding: 50px 20px;
  color: white;
  background-color: black;
  opacity: 0.7;
}

.film:hover > .film_description {
  display: block;
  z-index: 999;
}

.netflix_path {
  height: 750px;
  width: 500px;
}

.film_element {
  margin-bottom: 10px;
  text-align: left;
}

.film_plot {
  width: 400px;
  text-align: left;
}

.checked {
  color: yellow;
}
</style>