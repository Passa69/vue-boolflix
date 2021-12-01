<template>
  <main>
    <div v-for="(movie, i) in films" :key="i">
        <!-- Titolo -->
        <h4>{{ movie.title }}</h4>

        <!-- Titolo Originale -->
        <h5>{{ movie.original_title }}</h5>

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
    padding: 200px 50px;
}
</style>