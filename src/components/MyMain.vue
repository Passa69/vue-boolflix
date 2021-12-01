<template>
  <main>
    <!-- Titolo -->
    <h3>{{  }}</h3>

    <!-- Titolo Originale -->
    <h4>{{  }}</h4>

    <!-- Lingua -->
    <p>{{  }}</p>

    <!-- Voto -->
    <p>{{  }}</p>
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