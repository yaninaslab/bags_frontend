<template>
  <div id="app">
    <bags-list></bags-list>
  </div>
</template>

<script>
import BagsList from "./components/BagsList.vue";
export default {
  name: "App",
  components: {
    BagsList,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
