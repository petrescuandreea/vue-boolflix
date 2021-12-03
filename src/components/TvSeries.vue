<template>
  <div id="cards-container">
      <TvSerie  
      v-for="tvSerie in selectedTvSerie"
      :key="tvSerie.id" 
      :details="tvSerie"
      />
  </div>
</template>

<script>

import TvSerie from '@/components/TvSerie.vue';

export default {
  name: 'TvSeries',
  components: {
    TvSerie,
  },
  props: {
      selectedTvSerie: Array,
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