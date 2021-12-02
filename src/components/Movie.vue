<template>
    <div class="card" >
        <span>Titolo: {{ details.title }} </span>
        <span>Titolo originale: {{ details.original_title }}</span>
        <img v-if="details.original_language === 'it'" src='../assets/img/it.jpg'  alt="Italian Flag">
        <img v-else-if="details.original_language === 'en'" src='../assets/img/en.jpg'  alt="English Flag">
        <span v-else>Lingua originale non disponibile</span>
        <span>Voto: {{ details.vote_average }}</span>
    </div>
</template>

<script>


export default {
  name: 'Movie',
  props: {
      details: Object,
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