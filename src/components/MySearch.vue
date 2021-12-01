<template>
  <section>
      <input type="text" v-model="inputSearch" placeholder="Cerca un Film">

      <button @click.prevent="startSearching">Search</button>
  </section>
</template>

<script>
export default {
  name: 'MySearch',

  data() {
      return {
          inputSearch: "",
          userSearch: ""
      }
  },
  created() {
      this.startSearching();
  },
  methods: {
      startSearching() {
          this.userSearch = this.inputSearch;
          console.log(this.userSearch);
      }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
section {
    margin: 35px;
    float: right;

    input {
        margin-right: 10px;
        width: 200px;
    }

    button {
        padding: 7px;
        background-color: rgb(255, 91, 91);
        border-radius: 15px;
        border: rgb(255, 91, 91);
    }
}
</style>