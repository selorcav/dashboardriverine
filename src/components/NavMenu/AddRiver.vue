<template>
  <div>
    <v-card-actions class="px-0 py-0 menu-tab">
      <v-list-item-icon class="me-3">
        <v-icon color="white">  mdi-waves </v-icon>
      </v-list-item-icon>
      <v-btn depressed dark color="rgb(255, 0, 0, 0)">
        <v-list-item-content @click="show = !show">
          <v-list-item-title class="white--text subtitle-2">
            Agregar Río
          </v-list-item-title>
        </v-list-item-content>
      </v-btn>
    </v-card-actions>
    <v-expand-transition>
      <div v-show="show">
        <v-divider></v-divider>
        <v-card-text class="fields pb-0">
          <v-col class="pa-0 ma-0">
            <v-text-field class="pa-0 ma-0" label="Nombre"></v-text-field>
            <v-select :items="region" label="Región"></v-select>
            <v-select :items="caudal" label="Caudal"></v-select>
            <v-text-field class="pa-0 ma-0" label="Figura de la Cuenca"></v-text-field>
            <v-select :items="lecho" label="Tipo de lecho"></v-select>
            <v-select :items="clasificacion" label="Clasificación morfológica"></v-select>
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
      region: ["Región1","Región2","Región3",],
      caudal: ["Caudal1","Caudal2","Caudal3",],
      lecho: ["Lecho1","Lecho2","Lecho3",],
      clasificacion: ["Tipo1","Tipo2","Tipo3",],

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