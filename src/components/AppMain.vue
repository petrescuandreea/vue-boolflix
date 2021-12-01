<template>
  <div id="card-container">
      <Movie  
      v-for="movie in selectedMovie"
      :key="movie.id" 
      :details="movie"
      />
  </div>
</template>

<script>

import Movie from '@/components/Movie.vue';

export default {
  name: 'AppMain',
  components: {
    Movie,
  },
  props: {
      selectedMovie: Array,
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>