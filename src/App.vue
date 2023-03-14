<template>
  <navegation-bar />
  <router-view />
  <br>
  <piede-pagina />
</template>

<script>
import NavegationBar from "./components/NavegationBar.vue";
import PiedePagina from './components/PiedePagina.vue';
export default {
  components: {
    NavegationBar,
    PiedePagina,
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Nunito:wght@300&display=swap");
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-family: "Nunito", sans-serif;
}
</style>
