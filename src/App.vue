<template>
  <div id="app">
    <search-products></search-products>
  </div>
</template>

<script>
import SearchProducts from "./components/Searchproducts.vue";
export default {
  name: "App",
  components: {
    "search-products": SearchProducts
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  color: #2c3e50;
  margin-top: 60px;
}
</style>
