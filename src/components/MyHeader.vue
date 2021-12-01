<template>
  <header>
    <h1>BoolFlix</h1>

    <MySearch/>
  </header>
</template>

<script>
import MySearch from '@/components/MySearch.vue';

export default {
  name: 'MyHeader',
  components: {
    MySearch
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
}
</style>
