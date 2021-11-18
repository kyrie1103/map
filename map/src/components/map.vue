<template>
  <div id="map"></div>
</template>

<script lang="ts">
import { defineComponent, ref, onMounted } from "vue";
import * as L from "leaflet";
export default defineComponent({
  setup() {
    const map = ref();
    onMounted(() => {
      L.map("map").setView([51.505, -0.09], 13);
      L.tileLayer(
        "https://api.mapbox.com/styles/v1/mapbox/outdoors-v11/static/120.2149,30.2061,12.37,0/1280x1280?access_token=pk.eyJ1IjoieWtsMTIzIiwiYSI6ImNrdzRkMzRkNzgwMTcybm51ZzV1OXljcnkifQ.TUvZDJ_9S_omoTbmTA-IHA",
        {
          attribution:
            'Map data &copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors, Imagery © <a href="https://www.mapbox.com/">Mapbox</a>',
          maxZoom: 18,
        }
      ).addTo(map.value);
    });
    return {};
  },
});
</script>
<style lang="css">
#map {
  height: 180px;
}
</style>
