<template>
  <v-app class="relative">
    <NavDashboard />
    <v-btn class="btn-test" icon color="primary" @click="alert = !alert"> </v-btn>
    <v-main class="absolute main-content  mt-12">

          <v-alert class="pa-0 mb-0" :value="alert" transition="scale-transition">
            <CardContent />
          </v-alert>

    </v-main>
    <GoogleMap :latitude="-33.822321" :longitude="-69.963254" :title="'Mapa'" />
  </v-app>
</template>

<script>
import NavDashboard from "../components/NavDashboard.vue";
import GoogleMap from "../components/GoogleMap";
import CardContent from "../components/CardContent";

export default {
  name: "Dashboard",
  components: {
    NavDashboard,
    GoogleMap,
    CardContent,
  },
  data() {
    return {
      alert: false,
    };
  },
};
</script>

<style lang="sass" scoped>
.absolute
  position: absolute
  z-index: 3
.main-content
  width: 100%
.btn-test
  border: solid 2px white
  background-color: #2196F3
  position: absolute
  z-index: 10
  top: 70%
  left: 30%
</style>
