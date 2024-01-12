<template>
  <div>
    <nav class="navbar navbar-dark bg-success">
      <a class="navbar-brand" href="#">Shortify></a>
    </nav>
    <div class="mainContainer">
     <Home />
    </div>
  </div>
</template>

<script>
import Home from "./components/Home.vue";
export default {
  name: "App",
  components: {
    Home,
  },
};
</script>

<style>
  .mainContainer {
    max-width: 1170px;
    height: 100%;
    margin: 0 auto;
    padding: 0 20px;
  }
</style>