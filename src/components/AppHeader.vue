<template>
  <div id="header-wrapper">
      <form action="">
          <!-- aggancio v-model all'input per leggere in tempo reale quello che scrive l'utente  -->
          <input type="text" placeholder="Search movie" v-model="inputText">

          <!-- lancio l'evento search e gli passo un parametro per inviare i dati -->
          <button @click.prevent="getMovies">Search</button>
      </form>

  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'AppHeader',
  data() {
      return {
          //   variabile che salva l'endpoint dell'API
          apiUrl: "https://api.themoviedb.org/3/search/movie?api_key=16cc96ba36cde80dcf11f479cce8e348",
          //   salvo quello che  l'utente digita
          inputText: "",
          listMovies: [],
      }
  },
  methods: {
      getMovies() {
        //   richiesta axios 
        axios
        .get(`${this.apiUrl}&query=${this.inputText}`)
        .then((result) => {
            this.listMovies = result.data.results;
            console.log(this.listMovies);
        this.$emit('search', this.listMovies);
        });

        // azzerro il valore dell'input 
        this.inputText = "";
      },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>