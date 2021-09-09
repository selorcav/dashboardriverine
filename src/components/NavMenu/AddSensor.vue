<template>
  <div>
    <v-card-actions class="px-0 py-0 menu-tab">
      <v-list-item-icon class="me-3">
        <v-icon color="white"> mdi-leak </v-icon>
      </v-list-item-icon>
      <v-btn depressed dark color="rgb(255, 0, 0, 0)">
        <v-list-item-content @click="show = !show">
          <v-list-item-title class="white--text subtitle-2">
            Agregar Sensor
          </v-list-item-title>
        </v-list-item-content>
      </v-btn>
    </v-card-actions>
    <v-expand-transition>
      <div v-show="show">
        <v-divider></v-divider>
        <v-card-text class="fields pb-0">
          <v-col class="pa-0 ma-0 mt-1">
            <v-row>
              <v-col class="pa-0" cols="5">
                <v-subheader class="d-flex align-end">ID</v-subheader>
              </v-col>
              <v-col class="pa-0" cols="7">
                <v-text-field outlined value="1" label="ID"></v-text-field>
              </v-col>
            </v-row>
            <v-text-field class="pa-0 ma-0" label="Pila"></v-text-field>
            <v-select :items="tipo" label="Tipo"></v-select>
            <v-text-field class="pa-0 ma-0" label="Posición respecto a Pila"></v-text-field>
            <v-text-field class="pa-0 ma-0" label="Umbral Medio"></v-text-field>
            <v-text-field class="pa-0 ma-0" label="Umbral Alto"></v-text-field>
            <v-select :items="puente" label="Puente"></v-select>
          </v-col>
          <div class="d-flex justify-center">
            <v-btn @click="show = !show" class="mb-4 primary">Agregar</v-btn>
          </div>
        </v-card-text>
      </div>
    </v-expand-transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: false,
      tipo: ["Tipo1", "Tipo2", "Tipo3", "Tipo4"],
      puente: ["Puente1","Puente2","Puente3", ],
    };
  },
};
</script>
<style lang="sass">
.fields
  background-color: rgba(255,255,255,0.6)
// .v-input__slot
//   min-height: 45px !important
//   margin-bottom: 0
// .v-text-field__details
//   min-height: 0
//   height: 10px
</style>