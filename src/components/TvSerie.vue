<template>
    <div class="card" >
         <div class="cover-card">
            <img v-if="details.poster_path === null" src="https://images.everyeye.it/img-notizie/netflix-3-novita-gustarsi-streaming-weekend-d-un-fiato-v3-540119-900x900.webp" alt="Netflix logo">
            <img v-else :src="imgUrl + details.poster_path" alt="">
        </div>

        <div class="additional-info"> 
            <span><strong>Titolo:</strong> {{ details.name }} </span>
            <span><strong>Titolo originale:</strong> {{ details.original_name }}</span>
            <img v-if="details.original_language === 'it'" src='../assets/img/it.jpg'  alt="Italian Flag">
            <img v-else-if="details.original_language === 'en'" src='../assets/img/en.jpg'  alt="English Flag">
            <span v-else>Lingua originale non disponibile</span>
            <span><strong>Voto:</strong> {{ details.vote_average }}</span>
            <p v-if="details.overview === '' "><strong>Overview:</strong> non disponibile</p>
            <p v-else><strong>Overview:</strong> {{ details.overview }}</p>
        </div>
    </div>
</template>

<script>


export default {
  name: 'TvSerie',
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
    width: calc(100% / 3 - 150px);
    height: 500px;
    margin: 0 150px 50px 0;
    position: relative;
   
    

    .cover-card {
        border: 4px solid white;

        img {
            width: 100%;
            height: 500px;
            display: block;
        }

    }

    .additional-info {
        display: none;
        position: absolute;
        top: 40px;
        left: 20px;
        right: 20px;

        span {
            display: block;
        }

        img {
            width: 25px;
        }
    }
}

.card:hover {
    cursor: pointer;
    background-color: black;
}

.card:hover .additional-info {
    display: block;
    color: white;
}

.card:hover .cover-card img {
    display: none;
}

.card:hover .cover-card {
    height: 500px;
}
</style>