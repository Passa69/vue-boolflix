<template>
  <header>
    <h1>BoolFlix</h1>
  </header>
</template>

<script>
export default {
  name: 'MyHeader',

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
header {
  height: 100px;
  background-color: #000000;

  h1 {
    color: red;
    float: left;
    margin: 25px;
  }
}
</style>
