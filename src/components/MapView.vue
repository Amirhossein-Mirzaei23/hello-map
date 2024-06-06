<template>
    <div class="w-screen h-screen" >
      <l-map @ready="onReady" 
       @locationfound="onLocationFound" 
       
       ref="map" 
       v-model:zoom="zoom" 
       v-model:center="center"
       :min-zoom="minZoom"
       :max-zoom="maxZoom"
       >
       <l-geo-json :geojson="geojson" :options="geojsonOptions" />
        <l-tile-layer
          url="https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png"
          layer-type="base"
          name="OpenStreetMap"
        ></l-tile-layer>
        <l-marker
        :lat-lng="marker"
    
      >
    <l-popup><h1>hello</h1></l-popup>
    </l-marker>
      </l-map>
    </div>
  </template>
  
  <script setup >
  import "leaflet/dist/leaflet.css";
  import { ref } from 'vue'
  import { LMap, LTileLayer ,LMarker ,LPopup ,LGeoJson , } from "@vue-leaflet/vue-leaflet";
let  geojson= {
        type: "FeatureCollection",
        features: [
          // ...
        ],
      }
let geojsonOptions= {
        // Options that don't rely on Leaflet methods.
      }
  let zoom  = 15
  let minZoom = 5
  let maxZoom = 18
let center = ref([36.299, 59.601])


let marker = ref([36.361, 59.508]);

function onReady (mapObject) {
  mapObject.locate({setView: true, maxZoom: 16});
  
}
function onLocationFound(location){
  marker.value = location
  center.value = location
  console.log("find");
}

  </script>
  
  <style></style>