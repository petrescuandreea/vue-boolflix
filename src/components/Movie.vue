<template>
    <div class="card" >
        <span>Titolo: {{ details.title }} </span>
        <span>Titolo originale: {{ details.original_title }}</span>
        <span>
            Lingua: 
            <img :src="details.original_language === 'it' ? require('@/assets/img/flag-it.jpg') : require('assets/img/flag-en.jpg')" 
            :alt="details.original_language === 'it' ? 'Italian flag' : 'English flag'"> 
        </span>
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
}
</style>