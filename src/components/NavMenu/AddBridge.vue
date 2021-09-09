<template>
  <div>
    <v-card-actions class="px-0 py-0 menu-tab">
      <v-list-item-icon class="me-3">
        <v-icon color="white">  mdi-bridge </v-icon>
      </v-list-item-icon>
      <v-btn depressed dark color="rgb(255, 0, 0, 0)">
        <v-list-item-content @click="show = !show">
          <v-list-item-title class="white--text subtitle-2">
            Agregar Puente
          </v-list-item-title>
        </v-list-item-content>
      </v-btn>
    </v-card-actions>
    <v-expand-transition>
      <div v-show="show">
        <v-divider></v-divider>
        <v-card-text class="fields pb-0">
          <v-col class="pa-0 ma-0">
            <v-text-field
              class="pa-0 ma-0"
              label="Nombre Puente"
            ></v-text-field>
            <v-text-field
              class="pa-0 ma-0"
              label="Latitud"
              type="number"
            ></v-text-field>
            <v-text-field
              class="pa-0 ma-0"
              label="Longitud"
              type="number"
            ></v-text-field>
            <v-row>
              <v-col class="pa-0" cols="5">
                <v-subheader class="d-flex align-end">Nº de Pilas</v-subheader>
              </v-col>
              <v-col class="pa-0" cols="7">
                <v-text-field outlined value="1" label="Pilas"></v-text-field>
              </v-col>
            </v-row>
            <v-row>
              <v-col class="pa-0" cols="5">
                <v-subheader class="d-flex align-end"
                  >Largo del puente</v-subheader
                >
              </v-col>
              <v-col class="pa-0" cols="7">
                <v-text-field
                  outlined
                  value="1"
                  label="Largo"
                  suffix="mt"
                ></v-text-field>
              </v-col>
            </v-row>
            <v-text-field
              class="pa-0 ma-0"
              label="Profundidad de las fundaciones"
              type="number"
            ></v-text-field>
            <v-select
              :items="empresa"
              label="Empresa"
            ></v-select>
            <v-text-field class="pa-0 ma-0" label="Río"></v-text-field>
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
      pilas: 1,
      empresa: ['Empresa1', 'Empresa2', 'Empresa3', 'Empresa4'],
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