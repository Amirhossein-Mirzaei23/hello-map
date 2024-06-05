<template>
    <div style="height:600px;">
      <l-map @ready="onReady" 
       @locationfound="onLocationFound" 
       ref="map" 
       v-model:zoom="zoom" 
       v-model:center="center"
       :min-zoom="minZoom"
       :max-zoom="maxZoom"
       >
        <l-tile-layer
          url="https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png"
          layer-type="base"
          name="OpenStreetMap"
        ></l-tile-layer>
        <l-marker
        :lat-lng="marker"
        
      />
      </l-map>
    </div>
  </template>
  
  <script setup >
  import "leaflet/dist/leaflet.css";
  import { ref } from 'vue'
  import { LMap, LTileLayer ,LMarker } from "@vue-leaflet/vue-leaflet";

  let zoom  = 15
  let minZoom = 5
  let maxZoom = 18
let center = ref([36.299, 59.601])


let marker = ref([36.361, 59.508]);

function onReady (mapObject) {
  mapObject.locate();
  console.log(mapObject.locate());
}
function onLocationFound(location){
  marker.value = location
  center.value = location
}

  </script>
  
  <style></style>