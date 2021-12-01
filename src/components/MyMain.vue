<template>
  <main>
    <div v-for="(movie, i) in films" :key="i">
        <!-- Titolo -->
        <h3>{{ movie.title }}</h3>

        <!-- Titolo Originale -->
        <h4>{{ movie.original_title }}</h4>

        <!-- Lingua -->
        <p>{{ movie.original_language }}</p>

        <!-- Voto -->
        <p>{{ movie.vote_average }}</p>
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
    background-color: #434343;
    // debug
    height: 100vh;
}
</style>