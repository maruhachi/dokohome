<template>
  <section class="container">
      <GmapMap
        :center="{lat:38.26, lng:140.88 }"
        :zoom="9"
        map-type-id="terrain"
        style="width: 100%; height: 100%"
      >
        <GmapMarker
          :key="index"
          v-for="(m, index) in markers"
          :position="m.latLng"
          :clickable="true"
          :draggable="true"
          @click="center=m.position"
        />
      </GmapMap>
  </section>
</template>

<script>
export default {
  data() {
    return {
      markers: [
        { latLng: { lat: 38.25, lng: 140.87 } }
        , { latLng: { lat: 38.27, lng: 140.89 } }
      ],
      place: null,
    };
  }
};
</script>

<style>
.container {
  min-height: 100vh;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.vue-map-container {
  position: static !important;
}
</style>

