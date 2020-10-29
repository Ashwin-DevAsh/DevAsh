<template>
  <router-view></router-view>
</template>

<script>
import Homepage from "./components/Homepage";
import Vue from "vue";
import VueRouter from "vue-router";
import axios from 'axios'


Vue.use(VueRouter);

const routes = [
  { path: "/", component: Homepage },
  { path: "*", component: Homepage },
  { path: '/keyOS/PrivacyPolicy',
    component: Vue.component('manage-posts', function(resolve){
            axios.get("/KeyOS/PrivacyPolicy.html").then(response => {
              resolve({template: response.data})
          })
    })
  }
];

const router = new VueRouter({
  routes,
  mode: "history",
});

export default {
  name: "App",
  router,
};
</script>

<style>
html {
  scroll-behavior: smooth;
}

body {
  overflow-x: hidden;
  margin: 0%;
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
