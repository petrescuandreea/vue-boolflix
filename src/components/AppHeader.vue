<template>
  <div id="header-wrapper">
    <div id="logo">
      boolfix
    </div>
    <form action="">
      <!-- aggancio v-model all'input per leggere in tempo reale quello che scrive l'utente  -->
      <input type="text" placeholder="Search movie" v-model="inputText">

      <!-- lancio l'evento search e gli passo un parametro per inviare i dati -->
      <button @click.prevent="$emit('search', inputText)">Search</button>
    </form>

  </div>
</template>

<script>
// import axios from 'axios';

export default {
  name: 'AppHeader',
  data() {
      return {
         //   salvo quello che  l'utente digita
          inputText: "",
      }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
#header-wrapper {
  #logo {
    font-size: 40px;
    font-weight: bold;
    color: rgba(117,0,0,255);
    text-transform: uppercase;
  }
}
</style>