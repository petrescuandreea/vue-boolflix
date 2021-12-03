<template>
  <div id="cards-container">
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
  name: 'Movies',
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
#cards-container {
  background-color: rgba(67,67,67,255);
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start;
  padding: 50px;
}

</style>