<template>
  <div>
    <header>
      <!-- componente AppHeader  -->
      <!-- catturo l'evento lanciato da AppHeader => emit -->
      <AppHeader @search="searched" />
    </header>

    <main>
      <div v-if="listMovies.length === 0"></div>
      
      <!-- componente Movies / TvSeries -->
      <!-- invio il dato ricevuto da AppHeader a Movies e TvSeries=> props -->
      <div v-else>
      <Movies :selectedMovie="listMovies"/>
      <TvSeries :selectedTvSerie="listTvSeries"/>

      </div>

    </main>
  </div>
</template>

<script>
import axios from 'axios';
import AppHeader from '@/components/AppHeader.vue';
import Movies from '@/components/Movies.vue';
import TvSeries from '@/components/TvSeries.vue';

export default {
  name: 'ParentComponent',
  components: {
    AppHeader,
    Movies,
    TvSeries,
  },
  data() {
      return {
        //   salvo il dato inviato da AppHeader  
        //   film 
          choosedMovie: "",

        //   serie tv 
          choosedTvSerie: "",

        //   proprietà per creare l'URL
          urlMovies: "https://api.themoviedb.org/3/search/movie",
          urlTvSerie: "https://api.themoviedb.org/3/search/tv",
          apiKey: "16cc96ba36cde80dcf11f479cce8e348",

          listMovies: [],
          listTvSeries: [],
      }

  },
  methods: {
      getMovies() {
        //   richiesta axios per film
        axios
        .get(`${this.urlMovies}?api_key=${this.apiKey}&language=it-IT&query=${this.choosedMovie}`)
        .then((result) => {
            this.listMovies = result.data.results;
            console.log("movies" , result.data.results);
        });
      },

      getTvSeries () {
           //   richiesta axios per serie tv
        axios
        .get(`${this.urlTvSerie}?api_key=${this.apiKey}&language=it-IT&query=${this.choosedMovie}`)
        .then((result) => {
            this.listTvSeries = result.data.results;
            console.log("tvSeries" , result.data.results);
        });

      },

      // tengo traccia del film/serie cercata dall'utente
      searched(movies) {
          this.choosedMovie = movies;
          this.getMovies();
          this.getTvSeries();
      },
        
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
header {
    background-color: rgba(0,0,0,255);
    height: 100px;
}
main {
    background-image: url('https://store-images.s-microsoft.com/image/apps.63705.14253076346048674.def8e318-27bf-4909-8862-99111cdf551a.107916e7-cc10-423a-9434-90ccf92d46cd?mode=scale&q=90&h=720&w=1280');
    background-size: cover;
    background-position: center;
    min-height: calc(100vh - 100px);
}
</style>