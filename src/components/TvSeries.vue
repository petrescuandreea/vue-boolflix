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

</style>