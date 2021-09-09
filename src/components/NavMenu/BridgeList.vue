<template>
  <div>
    <v-card-actions class="px-0 py-0 menu-tab">
      <v-list-item-icon class="me-3">
        <v-icon color="white"> mdi-format-list-checkbox </v-icon>
      </v-list-item-icon>
      <v-btn depressed dark color="rgb(255, 0, 0, 0)">
        <v-list-item-content @click="show = !show">
          <v-list-item-title class="white--text subtitle-2">
            Ver Puentes Registrados
          </v-list-item-title>
        </v-list-item-content>
      </v-btn>
    </v-card-actions>
    <v-expand-transition>
      <div v-show="show">
        <v-divider></v-divider>
        <v-card-text class="fields">
          <v-list dense>
            <v-subheader>Lista de Puentes</v-subheader>
            <v-list-item-group v-model="selectedItem" color="primary">
              <v-list-item v-for="(item, i) in items" :key="i">
                <v-list-item-content>
                  <v-list-item-title v-text="item.text"></v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </v-list-item-group>
          </v-list>
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
      selectedItem: 1,
      items: [
        { text: "Puente 1" },
        { text: "Puente 2" },
        { text: "Puente 3" },
      ],
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