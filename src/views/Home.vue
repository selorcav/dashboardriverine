<template>
  <v-app class="bg-login">
    <v-row class="ma-0">
      <v-col class="d-flex justify-center align-center" cols="8" offset="2">
        <v-card elevation="8" width="100%" class="overflow-hidden">
          <v-row>
            <v-col
              class="bg-login-card d-none d-lg-block"
              cols="12"
              lg="5"
            ></v-col>
            <v-col class="px-0" cols="12" lg="7">
              <v-card-title class="ma-0 pa-0">
                <v-img
                  class="mx-auto"
                  src="../assets/riverine-logo.png"
                  max-height="150"
                  max-width="350"
                />
              </v-card-title>
              <v-tabs class="d-flex justify-center" v-model="tab">
                <v-tab class="tab-login"> Inicia sesión </v-tab>
                <v-tab class="tab-login"> Regístrate </v-tab>
              </v-tabs>
              <v-tabs-items v-model="tab">
                <v-tab-item>
                  <Login />
                </v-tab-item>
                <v-tab-item>
                  <Registro />
                </v-tab-item>
              </v-tabs-items>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
    </v-row>
  </v-app>
</template>

<script>
import Login from "../components/Login.vue";
import Registro from "../components/Registro.vue";

export default {
  name: "Home",
  components: {
    Login,
    Registro,
  },
  data() {
    return {
      tab: null,
    };
  },
};
</script>
<style lang="sass" scoped>
.bg-login
  background-image: url('../assets/fondo-bg.jpg')
  background-size: cover
  background-position: center
.bg-login-card
  background-image: url('../assets/fondo-login-card.jpg')
  background-size: cover
  background-position: center
.tab-login
  color: #cacaca !important
  background-color: lightgoldenrodyellow
.tab-login.v-tab--active
  color: #2970e2 !important
  background-color: gainsboro
</style>
