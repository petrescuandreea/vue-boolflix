<template>
  <div>
      <header>
      <!-- componente AppHeader  -->
      <!-- catturo l'evento lanciato da AppHeader => emit -->
      <AppHeader @searchMovie="searchedMovie"/>
    </header>

    <main>
      <!-- componente AppMain  -->
      <!-- invio il dato ricevuto da AppHeader a AppMain => props -->
      <AppMain :selectedMovie="listMovies"/>

    </main>
  </div>
</template>

<script>
import axios from 'axios';
import AppHeader from '@/components/AppHeader.vue';
import AppMain from '@/components/AppMain.vue';

export default {
  name: 'ParentComponent',
  components: {
    AppHeader,
    AppMain,
  },
  data() {
      return {
        //   salvo il dato inviato da AppHeader  
          choosedMovie: "",

        //   proprietà per creare l'URL
          urlMovies: "https://api.themoviedb.org/3/search/movie",
          apiKey: "16cc96ba36cde80dcf11f479cce8e348",

          listMovies: [],
      }

  },
  methods: {
      getMovies() {
        //   richiesta axios 
        axios
        .get(`${this.urlMovies}?api_key=${this.apiKey}&language=it-IT&query=${this.choosedMovie}`)
        .then((result) => {
            this.listMovies = result.data.results;
            console.log(this.listMovies);
        });

        // azzerro il valore dell'input 
        this.choosedMovie = "";
      },

      // tengo traccia del film richiesto dall'utente
      searchedMovie(movies) {
          this.choosedMovie = movies;
          this.getMovies();
      },
        
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>