<template>
  <div>
    <MapViewVue />
  </div>
</template>

<script>
import MapViewVue from './components/MapView.vue'


export default {
  name: 'App',
  components: {
    MapViewVue
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
  margin-top: 60px;
}
</style>
