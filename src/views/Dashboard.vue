<template>
  <v-app class="relative">
    <NavDashboard />
    <MarkerBridge />
    <GoogleMap :latitude="-33.822321" :longitude="-69.963254" :title="'Mapa'" />
  </v-app>
</template>

<script>
import NavDashboard from "../components/NavDashboard.vue";
import GoogleMap from "../components/GoogleMap";

import MarkerBridge from "../components/MarkerBridge.vue"

export default {
  name: "Dashboard",
  components: {
    NavDashboard,
    GoogleMap,
    MarkerBridge
  },
  data() {
    return {
      alert: false,
    };
  },
};
</script>

<style lang="sass" scoped>
</style>
