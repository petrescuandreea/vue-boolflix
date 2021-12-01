<template>
  <div id="app">
    <header>
      <!-- componente AppHeader  -->
      <AppHeader/>
    </header>

    <main>
      <!-- componente AppMain  -->
      <AppMain/>
    </main>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

export default {
  name: 'App',
  components: {
    AppHeader,
    AppMain,
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
