<template>
  <div class="bg-sky-300 bg-opacity-75" >
   
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

}
</style>
