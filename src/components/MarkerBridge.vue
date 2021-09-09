<template>
  <div class="flex-start-modal">
    <v-tooltip content-class=" pa-0" top>
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          class="btn-test"
          v-bind="attrs"
          v-on="on"
          @click="dialog = !dialog"
          icon
        ></v-btn>
      </template>
      <v-card class="mx-auto" max-width="344" outlined>
        <v-row>
          <v-col cols="6">
            <v-img
              height="200"
              src="https://i.imgur.com/f656uB3.jpg"
            ></v-img>
          </v-col>
          <v-col cols="6">
            <v-card-text class="pa-0 ma-0">
              <v-card-title class="px-0">Puente 1</v-card-title>
              <v-card-subtitle class="px-0">Río 1</v-card-subtitle>
              <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Temporibus?</p>
            </v-card-text>
          </v-col>
        </v-row>
      </v-card>
    </v-tooltip>
    <v-dialog max-width="500" scrollable v-model="dialog">
      <div>
        <v-card class="rounded-0" max-width="500">
          <card-puente />
          <CardRio />
          <card-sensor />
        </v-card>
      </div>
    </v-dialog>
  </div>
</template>

<script>
import CardPuente from "./CardPuente.vue";
import CardRio from "./CardRio.vue";
import CardSensor from "./CardSensor.vue";

export default {
  components: {
    CardPuente,
    CardRio,
    CardSensor,
  },
  data() {
    return {
      dialog: false,
    };
  },
};
</script>

<style lang="sass">
@import '../assets/css/mixin'
.btn-test
  border: solid 2px white
  background-color: #F44336
  position: absolute
  z-index: 4
  top: 70%
  left: 40%

.v-dialog
  width: auto
  margin: 0
  +for-ipad
    width: 80%
.v-dialog__content
  justify-content: flex-start
  align-items: flex-start
.v-dialog:not(.v-dialog--fullscreen)
  max-height: 100%
</style>