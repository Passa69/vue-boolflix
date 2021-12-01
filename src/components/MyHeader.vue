<template>
  <header>
    <h1>BoolFlix</h1>

    <section>
      <input type="text" v-model.trim="inputSearch" placeholder="Cerca un Film">

      <button @click="$emit('getInput', inputSearch)">Search</button>
    </section>
  </header>
</template>

<script>
export default {
  name: 'MyHeader',

  data() {
      return {
          inputSearch: ""
      }
  }
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

  section {
    margin: 35px;
    float: right;

    input {
        margin-right: 10px;
        width: 200px;
        border-radius: 15px;
        padding: 2px 5px;
    }

    button {
        padding: 5px 15px;
        background-color: rgb(255, 91, 91);
        border-radius: 15px;
        border: rgb(255, 91, 91);
    }
  }
}
</style>
