<template>
  <section class="container">
    <v-layout row justify-center align-center>
      <GmapMap
        :center="{lat:10, lng:10}"
        :zoom="7"
        map-type-id="terrain"
        style="width: 500px; height: 300px"
      >
        <GmapMarker
          :key="index"
          v-for="(m, index) in markers"
          :position="m.position"
          :clickable="true"
          :draggable="true"
          @click="center=m.position"
        />
      </GmapMap>
    </v-layout>
  </section>
</template>

<script>
import AppLogo from "~/components/AppLogo.vue";

export default {
  data() {
    return {
      markers: [
        { position: { lng: 10.2, lat: 10 } },
        { position: { lng: 10.1, lat: 10 } }
      ]
    };
  },
  components: {
    AppLogo
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
</style>

