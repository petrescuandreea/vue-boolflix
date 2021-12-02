<template>
    <div class="card" >
        <div class="cover-card">
            <img v-if="details.poster_path === null" src="https://images.everyeye.it/img-notizie/netflix-3-novita-gustarsi-streaming-weekend-d-un-fiato-v3-540119-900x900.webp" alt="Netflix logo">
            <img v-else :src="imgUrl + details.poster_path" alt="">
        </div>

        <div class="additional-info">
            <span>Titolo: {{ details.title }} </span>
            <span>Titolo originale: {{ details.original_title }}</span>
            <img v-if="details.original_language === 'it'" src='../assets/img/it.jpg'  alt="Italian Flag">
            <img v-else-if="details.original_language === 'en'" src='../assets/img/en.jpg'  alt="English Flag">
            <span v-else>Lingua originale non disponibile</span>
            <span>Voto: {{ details.vote_average }}</span>
        </div>
    </div>
</template>

<script>


export default {
  name: 'Movie',
  props: {
      details: Object,
  },
  data() {
      return {
          imgUrl: "https://image.tmdb.org/t/p/w342",
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.card {
    margin: 20px;

    span {
        display: block;
    }

    img {
        width: 25px;
    }
}
</style>