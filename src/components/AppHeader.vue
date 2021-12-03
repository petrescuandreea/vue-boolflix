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
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  padding: 30px 15px;

  #logo {
    font-size: 40px;
    font-weight: bold;
    color: rgba(117,0,0,255);
    text-transform: uppercase;
  }

  input {
    margin-right: 10px;
    padding: 2px 10px;
  }

  button {
    font-size: 15px;
    background-color: rgba(138,0,0,255);
    color: white;
    padding: 2px 5px;
    cursor: pointer;
    border: none;
  }

  button:hover {
    background-color: #f25757;
  }
}
</style>