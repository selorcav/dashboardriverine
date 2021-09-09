<template>
  <div class="text-center">
    <v-bottom-sheet max-width="100vw" v-model="sheet" inset>
      <template v-slot:activator="{ on, attrs }">
        <v-card-actions class="px-0 py-0 menu-tab">
          <v-list-item-icon class="me-3">
            <v-icon color="white"> mdi-format-list-checkbox </v-icon>
          </v-list-item-icon>
          <v-btn
            depressed
            dark
            color="rgb(255, 0, 0, 0)"
            v-bind="attrs"
            v-on="on"
          >
            <v-list-item-content>
              <v-list-item-title class="white--text subtitle-2">
                Ver Puentes Registrados
              </v-list-item-title>
            </v-list-item-content>
          </v-btn>
        </v-card-actions>
      </template>
      <v-sheet class="text-center">
        <h2 class="pt-4">Lista de puentes</h2>
        <v-divider/>
        <v-list class="pt-0" two-line>
          <v-list-item-group active-class="blue--text" multiple>
            <template>
              <v-list-item>
                <v-list-item-content>
                  <v-list-item-title> Puente 1</v-list-item-title>
                  <v-list-item-subtitle class="text--secondary">Región 1</v-list-item-subtitle>
                  <v-list-item-subtitle>Lugar 1</v-list-item-subtitle>
                </v-list-item-content>
              </v-list-item>
              <v-divider/>
              <v-list-item>
                <v-list-item-content>
                  <v-list-item-title> Puente 1</v-list-item-title>
                  <v-list-item-subtitle class="text--secondary">Región 1</v-list-item-subtitle>
                  <v-list-item-subtitle>Lugar 1</v-list-item-subtitle>
                </v-list-item-content>
              </v-list-item>
              <v-divider/>
            </template>
          </v-list-item-group>
        </v-list>

        <v-btn class="mt-6" text color="error" @click="sheet = !sheet">
          Cerrar
        </v-btn>
      </v-sheet>
    </v-bottom-sheet>
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: false,
      selectedItem: 1,
      items: [{ text: "Puente 1" }, { text: "Puente 2" }, { text: "Puente 3" }],
      sheet: false,
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
.v-bottom-sheet.v-dialog.v-bottom-sheet--inset
  max-width: 100vw
  width: inherit
</style>