<template>
  <div id="app">
    <header>
      <!-- componente AppHeader  -->
      <!-- catturo l'evento lanciato da AppHeader => emit -->
      <AppHeader @search="searchedMovie"/>
    </header>

    <main>
      <!-- componente AppMain  -->
      <!-- invio il dato ricevuto da AppHeader a AppMain => props -->
      <AppMain :selectedMovie="choosedMovie"/>
    </main>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

export default {
  name: 'App',
  components: {
    AppHeader,
    AppMain,
  },
  data() {
    return {
      // salvo il dato inviato da AppHeader 
      choosedMovie: [],
    }
  },
  methods: {
    // tengo traccia del film richiesto dall'utente
    searchedMovie(movies) {
      this.choosedMovie = movies;
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
