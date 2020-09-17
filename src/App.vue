<template>
  <div id="app">
    <b-container fluid>
      <Navigation />
      <main>
        <router-view />
      </main>
      <BottomFooter />
    </b-container>
  </div>
</template>

<script>
import Navigation from './components/navigation.vue'
import BottomFooter from './components/bottom-footer.vue'
export default {
  name: 'App',
  components: {
    Navigation,
    BottomFooter
  }
}
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
