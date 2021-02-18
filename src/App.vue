<template>
  <div id="app">
    <all-countries-list></all-countries-list>
  </div>
</template>

<script>
import AllCountriesList from "./components/AllCountriesList.vue";

export default {
  name: "App",
  components: {
    AllCountriesList,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
