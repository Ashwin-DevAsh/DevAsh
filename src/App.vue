<template>
  <Homepage></Homepage>
</template>

<script>
import Homepage from "./components/Homepage";

export default {
  name: "App",
  components: {
    Homepage
  }
};
</script>

<style>
html {
  scroll-behavior: smooth;
}

body {
  margin: 0%;
  overflow-x: hidden;
  font-family: "Poppins", sans-serif;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
